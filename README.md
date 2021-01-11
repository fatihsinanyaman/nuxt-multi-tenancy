

# Nuxt.JS Multi-Tenant Static Site Generation With CLI (without .env)
Generate static several sites from same nuxt instance with only one cli param 

## Requirement
- [cross-env](https://github.com/kentcdodds/cross-env) (for environment variable management)
## Usage
- Install [cross-env](https://github.com/kentcdodds/cross-env) package for development environment
	```
	npm install --save-dev cross-env
	```
- Edit your **scripts** property in **package.json**
	 ```json
	{
	  "scripts": {
	    "dev": "cross-env TENANT=$npm_config_tenant nuxt",
	    "build": "cross-env TENANT=$npm_config_tenant nuxt build",
	    "start": "cross-env TENANT=$npm_config_tenant nuxt start",
	    "generate": "cross-env TENANT=$npm_config_tenant nuxt generate"
	  },
	}
	```
- Edit **env** property in **nuxt.config.js**
	 ```json		
	 "env":  {
		"tenant": "process.env.TENANT ||  'default'"
	},
	```

- Run, Build & Generate with custom parameter
	```
	npm run generate --tenant=YourCustomTenantName
	```
- Use your **YourCustomTenantName** in project like **`process.env.tenant`** 
For example: [index.vue](https://github.com/fatihsinanyaman/nuxt-multi-tenancy/blob/main/pages/index.vue)  
