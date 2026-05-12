# Microsoft의 가장 가벼운 순정 Ubuntu 24.04 (noble) 베이스 이미지
FROM mcr.microsoft.com/devcontainers/base:noble

# Pi Agent 실행을 위한 Node.js 설치 (코드 실행용이 아닌 에이전트 구동용)
RUN curl -fsSL https://deb.nodesource.com/setup_20.x | bash - \
    && apt-get update \
    && apt-get install -y nodejs zsh \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*

# Pi Agent 전역 설치
RUN npm install -g @earendil-works/pi-coding-agent

# JUCE, C++ 개발 환경 설정
# apt-get 설치 중 시간대(tzdata) 등 상호작용 프롬프트가 뜨는 것 방지
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    cmake \
    gdb \
    pkg-config \
    libasound2-dev \
    libjack-jackd2-dev \
    libfreetype6-dev \
    libx11-dev \
    libxcomposite-dev \
    libxcursor-dev \
    libxext-dev \
    libxinerama-dev \
    libxrandr-dev \
    libxrender-dev \
    libwebkit2gtk-4.1-dev \
    libcurl4-openssl-dev \
    libgl1-mesa-dev \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*

ENV DEBIAN_FRONTEND=dialog

ENV SHELL /bin/zsh
USER vscode