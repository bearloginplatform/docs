---
sidebar_position: 3
---
# Авторизация с помощью провайдера

<pre>
<b>GET</b> v1/authorize
</pre>

Используйте данный роут для аутентификации через какой либо провайдер социальной сети. Успешный запрос вернет статус `302` и произведет редирект к указанному в `connection` провайдеру.

:::info
Данный тип аутентификации в основном поддерживается лишь с помощью браузеров, так как некоторые провайдеры могут запретить ввод данных для авторизации, в приложениях которые им не принадлежат.
:::

### Параметры запроса
<table>
  <thead>
    <th>Поле</th>
    <th>Описание</th>
  </thead>

  <tbody>
    <tr>
      <td>providerБ<font color="red">*</font></td>
      <td>Имя провайдера социальной сети, к примеру <code>gos-uslugi-oauth2</code></td>
    </tr>
   <tr>
      <td>redirect_uri<font color="red">*</font></td>
      <td>URL на который произойдет редирект после успешной авторизации</td>
    </tr>
  </tbody>
</table>

### Результат ответа
После успешной авторизации вернется статус `301`, произойдет redirect на указанный вами в параметрах `redirect_uri` и будут установлены соответствующие <a href="https://en.wikipedia.org/wiki/HTTP_cookie" rel="noreferrer" target="_blank">HTTP Cookie</a>