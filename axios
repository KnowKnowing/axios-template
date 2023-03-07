const axios = require("axios").default; //CommonJS 用法

class MyAxios {
  constructor(baseURL, timeout = 10000) {
    this.instance = axios.create({
      baseURL,
      timeout,
    });

    // 请求拦截
    this.instance.interceptors.request.use((config) => {
      return config;
    });

    // 响应拦截
    this.instance.interceptors.response.use((res) => {
      return res;
    });
  }

  request(config) {
    return new Promise((resolve, reject) => {
      this.instance
        .request(config)
        .then((res) => {
          resolve(res.data);
        })
        .catch((err) => {
          reject(err);
        });
    });
  }

  get(config) {
    return this.request({ ...config, method: "get" });
  }

  post(comfig) {
    return this.request({ ...comfig, method: "post" });
  }
}

//baseURL timeout
module.exports = new MyAxios("https://httpbin.org");
