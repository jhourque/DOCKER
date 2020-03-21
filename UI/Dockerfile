FROM  ubuntu

LABEL maintener "Jerome Hourquebie"

RUN apt-get update -y && \
    apt-get install -y xvfb x11vnc vim && \
    apt-get install -y firefox && \
    rm -rf /var/lib/apt/lists/* /var/cache/apt/* && \
    echo "Xvfb :1 -screen 0 1024x768x16 &> /tmp/xvfb.log &"   > /run.sh && \
    echo "x11vnc -passwd VNC -display :1 -N -forever &" >> /run.sh && \
    echo "export DISPLAY=:1" >> /run.sh && \
    echo "firefox" >> /run.sh && \
    echo "wait" >> /run.sh && \
    chmod +x /run.sh && \
    echo "export DISPLAY=:1" >> /etc/bash.bashrc

EXPOSE 5901

ENTRYPOINT ["/bin/sh", "/run.sh"]
