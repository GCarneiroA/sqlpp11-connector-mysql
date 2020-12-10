
set(sqlpp_mysql_SRCs
	connection.cpp
	prepared_statement.cpp
	char_result.cpp
	bind_result.cpp
	detail/connection_handle.cpp
)

add_library(sqlpp-mysql ${sqlpp_mysql_SRCs})
add_library(sqlpp11::mysql ALIAS sqlpp-mysql)

target_link_libraries(sqlpp-mysql
	INTERFACE date::date mariadb
	PUBLIC sqlpp11::sqlpp11)

target_include_directories(sqlpp-mysql INTERFACE
	"$<BUILD_INTERFACE:${sqlpp11-connector-mysql_SOURCE_DIR}/include>"
	$<INSTALL_INTERFACE:include>
)

install(TARGETS sqlpp-mysql DESTINATION lib)
