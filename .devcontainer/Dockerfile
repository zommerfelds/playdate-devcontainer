FROM ubuntu:22.04

# Install dependencies
RUN apt update && apt install -y \
    # General build requirements for Playdate
    build-essential \
    wget \
    unzip \
    gcc-arm-none-eabi \
    # For running the debugger and the simulator:
    gdb \
    libwebkit2gtk-4.0-37 

# Install Playdate SDK
RUN wget https://download.panic.com/playdate_sdk/Linux/PlaydateSDK-2.7.1.tar.gz -O playdate_sdk.tar.gz && \
    mkdir -p /opt/playdate_sdk && \
    tar -xzf playdate_sdk.tar.gz -C /opt/playdate_sdk --strip-components=1 && \
    rm playdate_sdk.tar.gz

# Prevent the simulator from showing anoying popups in the first run
RUN mkdir -p /root/.config/Playdate\ Simulator && echo '\
ShowPerfWarning=0\n\
LastRelease=2.7.1\n\
ShowElist=0\n' > /root/.config/Playdate\ Simulator/Playdate\ Simulator.ini

ENV PLAYDATE_SDK_PATH=/opt/playdate_sdk
ENV PATH="${PLAYDATE_SDK_PATH}/bin:${PATH}"

# Set up a directory to run the simulator. Devcontainer desktop-lite doesn't currently support sound, so we need to 
# run SDL in a mode that dumps sounds to a file. To save space we route that file to the null device:
RUN mkdir -p /opt/run && ln -s /dev/null /opt/run/sdlaudio.raw

CMD ["/bin/bash"]
