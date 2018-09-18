# Copyright 2018 Mike Dev
# Distributed under the Boost Software License, Version 1.0.
# See accompanying file LICENSE_1_0.txt or copy at http://www.boost.org/LICENSE_1_0.txt

cmake_minimum_required(VERSION 3.5)
project(boost-program_options)

add_library(boost_program_options STATIC)
add_library(Boost::program_options ALIAS boost_program_options)

target_include_directories(boost_program_options PUBLIC include)

file(GLOB SRC src/*.cpp)

target_sources(boost_program_options
    PRIVATE
        ${SRC}
)

target_link_libraries(boost_program_options
    PUBLIC
        Boost::any
        Boost::config
        Boost::core
        Boost::detail
        Boost::function
        Boost::iterator
        Boost::lexical_cast
        Boost::smart_ptr
        Boost::static_assert
        Boost::throw_exception
        Boost::type_traits
)
