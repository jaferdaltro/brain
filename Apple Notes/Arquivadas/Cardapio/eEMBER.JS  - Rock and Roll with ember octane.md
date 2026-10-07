---
apple-notes-id: 01A0D68B-88C3-441A-8BF9-83BC62CFF0D6
---
```
node -v 
16.20.1
```


```
ember --version
ember-cli: 5.3.0
node: 16.20.1
os: darwin arm64

```
**config/environment.js** contains the configuration of your application. Several things (like the rootURL of the application) are already defined for you, but you can also add new ones specific to your application. 

The **config/optional-features.json** file has a list of features that are not essential to the functioning 
of your app and can be switched on or off here. One example flag is jquery-integration. 

In **config/targets.js** you can define what browser versions are supported for your app. This allows the JavaScript transpiler, Babel, to conditionally polyfill browser features depending on whether the supported browsers you specified support it natively or not. 

**ember-cli-build.js** contains the build configuration of your project. It is responsible for recompiling all assets when a project file changes, and then outputs one bundle that contains all <u>JavaScript code and one</u> 
<u>for the CSS</u>. It runs all preprocessors, copies files from one place to another and concatenates 3rd-party libraries. This processing is called the asset pipelin 

### Dynamic Expression 
Dynamic expression is anything enclosed in mustaches
{{ …}}

JIT - Tailwind 3

- Handlebar’s fail-softness