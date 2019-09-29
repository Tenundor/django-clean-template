Это чистый шаблон Django проекта, с которым можно быстро начать разработку. В шаблон входит конфиг Systemd, nginx, gunicorn.

Установка представляет собой просто указание Python интерпретатора и названия домена, запустите:

```bash
./install.sh
```

В конфиге Django заполните настройки базы данных (`src/config/settings.py`).

Посмотреть статус gunicorn демона:

```bash
sudo systemctl status gunicorn
```

Лог gunicorn'а (`-f` как в `tail -f`):

```bash
sudo journalctl -fu gunicorn
```

После изменения systemd конфига надо перечитать его и затем перезапустить юнит:

```bash
sudo systemctl daemon-reload
sudo systemctl restart gunicorn
```
