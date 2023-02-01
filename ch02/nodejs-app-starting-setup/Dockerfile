# Docker Hub 에 node 이미지
FROM node

# Docker 모든 후속 명령이 해당폴더 내부에서 실행될것임을 알림
WORKDIR /app

# package.json  파일도 /app에 복사한다
COPY package.json /app

# 노드 애플리케이션 경우 모든 종속성을 설치하기위해 npm install 수행
# 이미지에서 명령을 실행 -> RUN
RUN npm install

# 로컬머신에 있는 파일이 이미지에 들어가야된다
# 경로지정
# 첫번째 . -> Dockerfile 포함된 동일한 폴더 경로
# 두번째 /app -> 도커 컨테이너의 현재 작업 디렉토리
COPY . /app

# 컨테이너 내부의 노드 애플리케이션에서 포트 80을 수신할때 
# 컨테이너는 그 포트를 우리의 로컬머신에 노출하지 않는다
# EXPOSE - 로컬시스템에 특정포트를 노출하고 싶을때
EXPOSE 80

# CMD - 이미지를 기반으로 컨테이너가 시작될때 실행
CMD ["node","server.js"]