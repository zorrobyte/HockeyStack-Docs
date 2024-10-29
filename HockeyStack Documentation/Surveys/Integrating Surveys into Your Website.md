# Integrating Surveys into Your Website

In order to use HockeyStack Surveys, you need to add a new snippet to your website. This snippet is almost the same as the one in the [original HockeyStack integration guide](https://www.notion.so/The-Definitive-Guide-to-Your-Initial-Integration-1fc18626ee81470fa30e5be4dfc5ca51?pvs=21). The only difference is the source of the script:

```jsx
<script async data-apikey="YOUR_API_KEY" data-cookieless src="https://cdn.jsdelivr.net/npm/hockeystack-surveys-tool@latest/hockeystack-surveys.min.js"></script>
```