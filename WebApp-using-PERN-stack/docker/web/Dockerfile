# ====================================== react ================================================
# build environment
FROM node:12.2.0-alpine
WORKDIR /app
ENV PATH /app/node_modules/.bin:$PATH
COPY package.json /app/package.json
RUN npm install --silent
RUN npm install react-scripts@3.0.1 -g --silent
RUN npm install pm2 -g            # 全局安装 pm2 # 曝露容器端口
COPY . /app
RUN npm run build

EXPOSE 8080                       
CMD ["pm2-runtime", "./server.js"]   # 执行启动命令

