---
layout: post
title: How to move Scroll to top on new page (React-router)
subtitle: by Daniel Taehoon Kang
bigimg: /img/backdesktop.jpg
tags: [React, Router, Web]
date: 2019-01-15
---


[Here is Guide about scroll-restoration](https://reacttraining.com/react-router/web/guides/scroll-restoration)
### Let's try it out!


1.Make the Util component

```javascript
class ScrollToTop extends Component {
  componentDidUpdate(prevProps) {
    if (this.props.location !== prevProps.location) {
      window.scrollTo(0, 0);
    }
  }

  render() {
    return this.props.children;
  }
}

export default withRouter(ScrollToTop);
```

2.Render it at the top of your app, But you should render below Router
If you are using redux store, then you can write code on top level page like this:

```javascript
 <Provider store={store}>
      <BrowserRouter>
      <ScrollToTop>
        <App />
        </ScrollToTop>
      </BrowserRouter>
    </Provider>,
```

then you can move scroll to top on every single page in your app!

