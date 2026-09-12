cmake_minimum_required(VERSION 4.2)
project(Semester_Project)

set(CMAKE_CXX_STANDARD 14)

include_directories(.)

add_executable(Semester_Project
        "Semester Project/x64/Debug/.NETFramework,Version=v4.7.2.AssemblyAttributes.cpp"
        Graph.h
        GUIObserver.h
        Initializer.h
        Intersection.h
        main.cpp
        Manager.h
        Observer.h
        Queue.h
        Road.h
        Subject.h
        trafficSimulation.cpp
        trafficSimulation.h
        Vehicle.h)
