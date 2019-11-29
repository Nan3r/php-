# PHP 后门方式

## 文件包含

1. include
2. include_once
3. require
4. require_once
5. file_get_contents

## 系统命令执行

1. exec
2. system
3. popen
4. passthru
5. proc_open
6. pcntl_exec
7. shell_exec
8. curl_exec
9. curl_multi_exec
10. ``
11. escapeshellcmd

## 代码执行

```
eval
preg_replace
assert
call_user_func
call_user_func_array
create_function
ob_start
array_map
usort(), uasort(), uksort()
array_filter()
array_reduce()
array_diff_uassoc(), array_diff_ukey()
array_udiff(), array_udiff_assoc(), array_udiff_uassoc()
array_intersect_assoc(), array_intersect_uassoc()
array_uintersect(), array_uintersect_assoc(), array_uintersect_uassoc()
array_walk(), array_walk_recursive()
xml_set_character_data_handler()
xml_set_default_handler()
xml_set_element_handler()
xml_set_end_namespace_decl_handler()
xml_set_external_entity_ref_handler()
xml_set_notation_decl_handler()
xml_set_processing_instruction_handler()
xml_set_start_namespace_decl_handler()
xml_set_unparsed_entity_decl_handler()
stream_filter_register()
set_error_handler()
register_shutdown_function()
register_tick_function()
```



## 数据传递

1. GET
2. POST
3. COOKIE
4. SERVER
5. REQUEST
6. ENV
7. GLOBALS
8. php://input
9. getenv
10. session/cookie
11. extract
12. parse_str
13. mb_parse_str
14. import_request_variables
15. unserialize

## 文件操作

```
copy/rmdir/chmod/delete/fwrite/fopen/readfile/fpassthru/move_uploaded_file/file_put_contents/unlink/upload/opendir/fgetc/fgets/ftruncate/fputs/fputcs
```

## 数据库操作

```
select/insert/update/delete/order by/group by/limit/in(/stripslashes/urldecode
confirm_phpdoc_compiled/mssql_pconnect/mssql_connect/crack_opendict/snmpget/ibase_connect
```

## 敏感信息，源代码泄露

1. phpinfo
2. highlight_file
3. show_source
4. parse_ini_file 

## 代码加密

1. iconv
2. mb_convert_encoding
3. base64_decode
4. gzinflate
5. gzuncompress
6. gzdecode
7. str_rot13 

## php.ini

```
safe_mode = off ( a lot of shit cannot be done with this on )
disabled_functions = N/A ( no one,we want all )
register_globals = on ( we can set variables by request )
allow_url_include = on ( for lfi/rfi )
allow_url_fopen = on ( for lfi/rfi )
magic_quotes_gpc = off ( this will escape ‘ ” \ and NUL’s with a backslash and we don’t want that )short_tag_open = on ( some scripts are using short tags,better on )
file_uploads = on ( we want to upload )
display_errors = on ( we want to see the script errors,maybe some undeclared variables? )
open_basedir 限制访问目录
display_errors = off 显示错误信息
auto_prepend_file = on 在每个页面之前被载入
auto_append_file = on 在每个页面之后被载入

```
