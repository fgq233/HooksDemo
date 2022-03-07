# HooksDemo

### 注意：
1. 只在最顶层使用Hook, 不要在循环，条件或嵌套函数中调用 Hook
2. 只在React函数中调用Hook, 不要在普通的JavaScript函数中调用 Hook, 可以：  
>在React的函数组件中调用Hook  
>
>在自定义Hook中调用其他 Hook  
>
### 常用
#### 1、react原生
##### useState
```		
const [state, setState] = useState(0);			setState(3)
const [state, setState] = useState({value: ''});	setState({value: 'X'})
```	
##### useEffect
```
componentDidMount/componentDidUpdate/componentWillUnmount
useEffect(()=>{},[])  			= componentDidMount
useEffect(()=>{})	  		= componentDidMount + componentDidUpdate
useEffect(()=>{return ()=>{}},[])	= componentWillUnmount
useEffect(()=>{},[params])  		仅在params更改时更新，如果数组中有多个元素，即使只有一个元素发生变化，React 也会执行 effect
```
##### useRef
```
const refContainer = useRef(initlVal);	
返回一个可变的 ref 对象,在组件的整个生命周期内持续存在,其.current 属性被初始化为传入的参数initlVal
当 ref 对象内容发生变化时, useRef 并不会通知你, 变更.current 属性不会引发组件重新渲染
```	
##### useReducer
##### useContext：用于组件间共享状态，不常用
##### useLayoutEffect

#### 2、Redux
useSelector		mapStateToProps
useDispatch		mapDispatchToProps

#### 3、react-navigation
useNavigation
useNavigationState
useFocusEffect
