add_library(sqlpp-mysql
		connection.cpp
		prepared_statement.cpp
		char_result.cpp
		bind_result.cpp
		detail/connection_handle.cpp)

target_link_libraries(sqlpp-mysql PUBLIC date::date sqlpp11::sqlpp11)

install(TARGETS sqlpp-mysql DESTINATION lib)
