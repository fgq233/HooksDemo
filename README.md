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

const [state, setState] = useState(() => {
  const initialState = someExpensiveComputation(props);
  return initialState;
});
initialState 参数只会在组件的初始渲染中起作用，后续渲染时会被忽略。
可以传入一个函数，在函数中计算并返回初始的 state，此函数只在初始渲染时被调用
```	
##### useEffect
```
componentDidMount/componentDidUpdate/componentWillUnmount
    
    componentDidMount + componentDidUpdate
    useEffect(() => {
        console.warn('useEffect' + config);
    });
    
    componentDidMount + componentDidUpdate + componentWillUnmount
    useEffect(() => {
        console.warn('useEffect' + config);
        return () => {
            console.warn('useEffectX' + config);
        };
    });
  
  
    componentDidMount
    useEffect(() => {
        console.warn('useEffect' + config);
    }, []);
    
    componentDidMount + componentWillUnmount
    useEffect(() => {
        console.warn('useEffect' + config);
        return () => {
            console.warn('useEffectX' + config);
        };
    }, []);

    componentDidMount一次 + 每次config改变时调用
    useEffect(() => {
        console.warn('useEffect' + config);
    }, [config]);
    
    componentDidMount + componentWillUnmount + 每次config改变时调用
    useEffect(() => {
        console.warn('useEffect' + config);
        return () => {
            console.warn('useEffectX' + config);
        };
    }, [config]);
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
