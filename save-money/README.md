# save-money

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Run your unit tests
```
npm run test:unit
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

### What needs to be done
1. How to display/render data in template - first name
2. How to display/render data from computed property in template
3. How to display data from computed if data is an array using loop
Example: [{ name: 'Norbi' }, { name: 'Erwin' }]
4. How to import a component and use it
5. How to send props to a component
6. Create a list component and an item component. The list component will receive the array as a prop, will loop thru the array and send each item to the item component as a prop.

Next level
1. Import and use axious
2. Find a free api endpoint and retrieve some data
3. Send it to products and list it


Next steps:

4. Create a constant file called endpoints. Folder structure should be:
constants/endpooints.ts

Create an array, with a string endpoint (for now, more to come).

Instead of manually putting the endpoint into the axios function, let's use the constant file for that.

5. Add at least 2-3 endpoints to the endpoint array and try to call each endpoint every 10 seconds. You will need to loop thru the array and use either interval, or setTimeout to wait the 10 seconds. We don't want to spam the system, so we have to make sure we don't make unlimited endpoint calls to the api. This is considered done, when you see in the network tab, the 10 seconds between the calls