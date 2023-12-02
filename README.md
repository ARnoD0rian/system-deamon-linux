# system-deamon-linux
Для запуска программы необходим компилятор MINGW для С++.
Для того, чтобы запустить демона необходимо скомпилировать файл backup_config.cpp. Затем необходимо добавить конфигурации для system. Для этого необходимо в терминале вписать следующие команды:
touch/etc/systemd/system/backup.service
chmod664/etc/systemd/system/backup.service
nano /etc/systemd/system/backup.service
После этого в открывшемся файле необходимо вписать следующие команды:
[Unit]
Description=Backup Daemon
[Service]
ExecStart=/home/parallels/Desktop/deamon_backup/g
Restart=always
    	[Install]
WantedBy=multi-user.target"
После этого необходимо запустить демона в systemd: systemctl start backup.service. 
Наконец добавить в автозагрузку:
systemctl enable test-script.service
Для изменения конфигурации демона необходимо скомпилировать файл backup_config.cpp и при запуске передать в него новые параметры.

