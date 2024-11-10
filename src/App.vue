<template>
  <div id="app">
    <p1>Quote getter, v.1.0</p1>
    <br/>
    <button type="submit" @click="quoteApi.getQuote">Get random quote</button>
    <br/>
    <p2>Random quote of the day:</p2>
    <br/>

  </div>
</template>

<script>
import axios from "axios";

const instance = axios.create({
  baseURL: `http://api.quotable.io`//,
  /* Если добавить этот config - тогда запрос не будет работать.
                withCredentials: false,
                headers: {*/
                     // "Accept": "*/*",
                  //"Accept-encoding": "gzip, deflate",
                  //"content-type": "application/json",
               //   "connection": "keep-alive"
                //      }
});

  export const quoteApi = {
    data() {
      return {
        quote: [],
      }
    },
  getQuote() {
 return instance.get(`/random`)
       .then(response => this.quote = response.data);
}
}
</script>