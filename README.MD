# TTTTT-project-2026  

Студент: 372606

## Описание выполненных заданий

1. Сеть. Настроен DHCP, имя хоста `TTTTT-2026.domain.local`, проверена связность - `ping.out` 

2. ПО. Обновление системы, установка `nginx`, `libcap-ng-utils`, локальная установка `tcpdump` через `rpm` - `dnf.out`, `history.out` 

3. Файловые системы. Создан раздел `/dev/sdb1` (ext4, метка `TTTTT_WEB`), настроено автомонтирование в `/TTTTT-web` - `fstab`, `stat.out` 

4. Сервисы. Веб-сервер `nginx` запущен и добавлен в автозагрузку | `journalctl.out` 

5.1. DAC. Созданы пользователи (5501-5503) и кураторы (4444). Настроен `setgid` и Default ACL для `/data/TTTTT-2026` - `passwd`, `group`, `stat.out` 

5.2. Capabilities. Снят set-UID с `tcpdump`, выданы привилегии `cap_net_raw,cap_net_admin+ep` - `getcap.out` 

5.3. SELinux. Режим `Enforcing`. Для `/TTTTT-web` установлен контекст `httpd_sys_content_t` - `getenforce.out`, `stat.out` 

6. Аутентификация. Запрещен локальный вход кураторам (`pam_access`). Политика паролей: 90 дней, мин. длина 12 символов - `shadow`, `pwquality.conf`

7. Тестирование. Создана страница `index.html`, успешно отдается веб-сервером - `curl.out`, скриншот 
