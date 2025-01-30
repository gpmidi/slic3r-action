FROM keyglitch/docker-slic3r-prusa3d:latest

LABEL "name"="Slic3r gcode Action"
LABEL "maintainer"="davidk <kdavid+slic3r+action@gmail.com>"
LABEL "version"="1.0.0"

LABEL "com.github.actions.name"="Slic3r Gcode Action"
LABEL "com.github.actions.description"="Calls Prusa3d's Slic3r fork to generate gcode from STLs"
LABEL "com.github.actions.icon"="package"
LABEL "com.github.actions.color"="blue"

COPY entrypoint.sh /entrypoint.sh
COPY LICENSE-slic3r /

USER root

RUN apt-get update && apt-get install -y jq curl wget

RUN mkdir -p /config \
 && wget -o /config/PrusaSlicer_config_bundle.ini "https://github.com/suchmememanyskill/PrusaSlicer-Ender3-v3-SE-Config/releases/download/v1.2.3/PrusaSlicer_config_bundle.ini"

ENTRYPOINT ["/entrypoint.sh"]
