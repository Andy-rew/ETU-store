## ETU-forms

### Приглашение и регистрация новых пользователей

Приглашать новых пользователей может:

1. `system-admin` - приглашает системных администраторов и администраторов процессов
2. `process-admin`- приглашает участников/менеджеров/экспертов в любой процесс
3. `user`, который является менеджером процесса - приглашает участников/менеджеров/экспертов только в те процессы, за которыми он закреплен


Процесс приглашения, например за `system-admin` (для остальных ролей - аналогично):

1. `POST /system-admin/user/invite` - В результате будет отправлено письмо со ссылкой для регистрации на указанный email, в ссылку включается код активации пользователя, статус пользователя `UserStatusEnum.invited`
2. `POST /auth/sign-up` -  Ожидается пароль пользователя и код активации из ссылки, которая была в письме, после чего статус пользователя `UserStatusEnum.activated`

### Добавление/ удаление пользователя  в/из процесса

![](images/process_add_remove_user.png)