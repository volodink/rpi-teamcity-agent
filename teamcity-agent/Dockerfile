FROM hypriot/rpi-java

RUN apt-get update && \
	apt-get install -y wget curl build-essential gcc g++ make cmake doxygen tree astyle python python3 python-pip python3-pip

RUN pip install pytest

RUN pip install -U platformio

RUN wget -v https://download.jetbrains.com/teamcity/TeamCity-10.0.4.tar.gz && \
    tar -xzvf TeamCity-10.0.4.tar.gz && \
    rm *.tar.gz

ADD buildAgent.properties TeamCity/buildAgent/conf/

EXPOSE 8111 8090

ENTRYPOINT TeamCity/buildAgent/bin/agent.sh run






