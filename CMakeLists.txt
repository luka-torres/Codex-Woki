cmake_minimum_required(VERSION 3.13)
project(pico_w_keypad_led C CXX)

# This source is written in Arduino style (setup/loop + Keypad library).
# Build and upload using Arduino-Pico / PlatformIO, or run in Wokwi.

add_custom_target(note ALL
  COMMAND ${CMAKE_COMMAND} -E echo "Use Arduino-Pico toolchain for building src/main.cpp"
)
