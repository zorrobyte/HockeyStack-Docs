# React

Whether you call it a framework, a library, or a lifestyle, React is a very popular tool to build sites with. Our tracking script works with SPAs (single page application) too but the code to embed it to your site is a little more complicated.

There are many ways to embed custom script tags into your site, see [React Helmet](https://www.npmjs.com/package/react-helmet) for an npm package. The solution below does not require any package installation. It uses [Hooks](https://reactjs.org/docs/hooks-effect.html), which were introduced in React 16.8, to call the script once the component is mounted.

Don’t forget to replace `YOUR_API_KEY` with your actual API key.

```jsx
useEffect(() => {
  const script = document.createElement('script');
  script.src = "https://cdn.jsdelivr.net/npm/hockeystack@latest/hockeystack.min.js";
  script.async = true;
  script.dataset.apikey = "YOUR_API_KEY";
  script.dataset.cookieless = 1;
  script.dataset.autoIdentify = 1;
  document.head.appendChild(script);
}, []);

```