cmake_minimum_required(VERSION 3.22)
project(HyeonAudioPlugins VERSION 1.0.0)

# JUCE FRAMEWORk is loaded only once in entire porject
add_sudirectory(JUCE)

# Register the individual plugin folders to be built.
# add_subdirectory(Plugins/[directory])