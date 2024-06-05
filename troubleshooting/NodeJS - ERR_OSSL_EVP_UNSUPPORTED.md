
- [builtin.com - How To Fix the ERR_OSSL_EVP_UNSUPPORTED Error in Node.js | Built In](https://builtin.com/software-engineering-perspectives/err-ossl-evp-unsupported)

> [!important] NODE.js ERR_OSL_EVP_UNSUPPORTED ERROR Explained
> `ERR_OSL_EVP_UNSUPPORTED` is an error that occurs in Node.js 17 when your application or one of its modules attempts to use an algorithm or key size that’s no longer allowed by default in OpenSSL 3.0. You can fix it by either downloading the latest Node.js LTS version or using the `--openssl-legacy-provider`.

- As of NodeJS 17, this error can can be worked around by using the `--openssl-legacy-provider` option when running Node. For frontend projects this typically means prepending node commands with a `NODE_OPTIONS` env var as follows:

```bash
NODE_OPTIONS=--openssl-legacy-provider npm run start
```
