# battery-performance

# Requirements

- Docker (https://docs.docker.com/install/)
- Battery Historian (https://github.com/google/battery-historian)
- platform-tools from Android SDK ( adb )

# How to run

1. Run docker daemon
2. start docker image
`docker -- run -p <port>:9999 gcr.io/android-battery-historian/stable:3.0 --port 9999`
where <port> can be any available port.
3. Plug android device 
4. Run `adb shell dumpsys batterystats --reset` - this command resets saved information about battery drain
5. Make actions inside tested app
6. Run `adb bugreport bugreport.zip` - output of this command is .zip file that contains information about recent battery drain 
7. Go to http://localhost:<port>
8. Import .zip file
  
  
