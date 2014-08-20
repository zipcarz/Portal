winmap2
=======
  - /var/log/httpd/access_log
  - /var/log/httpd/error_log
  - /opt/misc/*.log
  - /home/**/*.log
  - /var/log/mysqld.log
  - /var/run/mysqld/mysqld-slow.log
exclude_files:
  - old
  - 200\d
hostname: www42  # override OS hostname
parse_fields: syslog   # predefined regex name or double-quoted regex
prepend: '0xDEADBEEF: '  # prepend this before every log message
exclude_patterns:
  - exclude this
  - \d+ things
destination:
  host: logs.papertrailapp.com
  port: 8080  # NOTE: change this to YOUR papertrail port!
new_file_check_interval: 5 # Check every 5 seconds
