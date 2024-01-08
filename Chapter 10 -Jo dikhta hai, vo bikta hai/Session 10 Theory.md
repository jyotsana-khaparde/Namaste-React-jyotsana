## Q: What is SCSS and SASS?

## Q: What are the ways to write CSS?
A: There are several ways to write CSS using libraries or frameworks along with default styles.
- Can use inline styles
- Can write css in default index.css file
- Can use SCSS and SASS
- Can use styled-components
- Material UI - they give pre build style components
- Bootstrap
- Chakra UI - https://chakra-ui.com/ 
- Ant design - https://ant.design/ 
- Tailwind CSS

## Q: What is PoseCSS?
A: It's a tool. tailwind CSS use PoseCSS behind the scenes for transforming `CSS with javascript`. 

## Q: What happens when we do `npx tailwindcss init`?
A: `npx tailwindcss init` means we are initializing the tailwind CSS into our repository. when we run this command, it creates a new file `tailwind.config.js` this is the configuration file for tailwind. your bundler (parcel) will use `.posecssrc` to understand tailwind.