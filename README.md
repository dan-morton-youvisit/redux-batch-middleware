# redux-batch-middleware

> Batch Redux actions

[![npm version](https://img.shields.io/npm/v/redux-batch-middleware.svg?style=flat-square)](https://www.npmjs.com/package/redux-batch-middleware)

Batch [middleware](http://rackt.github.io/redux/docs/advanced/Middleware.html) for Redux. Inspired by [redux-batched-actions](https://github.com/tshelburne/redux-batched-actions).

## Install

```
npm install --save redux-batch-middleware
```

## Usage

Add as middleware:

```js
    import { applyMiddleware, createStore } from 'redux';
    import { batch, batching } from 'redx-batch-actions';
    import reducers from './reducers';

    let middleware = [batch];

    let store = applyMiddleware(...middleware)(createStore)(batching(reducers));
```

Dispatch multiple actions:

```js
    store.dispatch([action1, action2]);
```

## API

### batch

Redux middleware which converts a dispatched array of actions to a batch action.

### batching(reducer)

#### reducer

Type: `function`

A reducer that should be able to handle batched actions, most likely the root reducer.

## License

MIT