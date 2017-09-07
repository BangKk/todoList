[![Build Status](https://travis-ci.org/BangKk/todoList.svg?branch=master)](https://travis-ci.org/BangKk/todoList)

## 说明
- 这是官方的一个 todoList example 。通过例子了解 react-redux 。

## API

### mapStateToProps
connect 方法的第一个参数，作用是将所需的 state 映射到 props 传入组件。

### mapDispatchToProps
connect 方法的第二个参数，作用是将需要绑定的响应事件注入到组件上

```jsx
// 将需要的state的节点注入到与此视图数据相关的组件上
const mapStateToProps = (state, ownProps) => {
  return {
    active: ownProps.filter === state.visibilityFilter
  }
}

// 将需要绑定的响应事件注入到组件上
const mapDispatchToProps = (dispatch, ownProps) => {
  return {
    onClick: () => {
      dispatch(setVisibilityFilter(ownProps.filter))
    }
  }
}

const FilterLink = connect(
  mapStateToProps,
  mapDispatchToProps
)(Link)

```