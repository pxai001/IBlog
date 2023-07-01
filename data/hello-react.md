## 项目创建

### yarn

````shell
yarn create react-app my-app
````

### npm

```shell
npx create-react-app my-app
```

### 没有 webpack.config.js

```shell
执行后有 config 文件夹
npm run eject
```

## 组件

### 组件类型

#### 函数组件

```js
function Home(props) {
    // 依赖设置为空，表示为只有第一次加载时执行，避免重复请求
    // react@v18 app.js 中使用 <React.StrictMode> 严格模式下， useEffect 会执行两遍，但生产环境不影响
   let ref = useRef();
    useEffect(() => {
        console.log('请求 API');
    }, [])
    return (
        <div ref={ref}>
            Home
        </div>
    )
}

export default Home;
```

#### 类组件

```js
class Home extends React.Component {
    render() {
        return <h1>Hello, {this.props.name}</h1>;
    }
}
```

### 组件用法

#### 变量

```js
const [navActive, setNavActive] = useState(0);
```

#### 参数

```js
function Home(props) {
    return (
        <div>
            {props.name}
        </div>
    )
}

export default Home;
```

### 第三方组件

#### 字节跳动图标组件

1. 安装 : yarn add @icon-park/react
2. 引入 css：import '@icon-park/react/styles/index.css';
3. 引入图标：import {Home} from '@icon-park/react';
4. 完整文档：https://github.com/bytedance/IconPark/blob/master/packages/react/README.md
5. 图标库：https://iconpark.oceanengine.com/official

## 路由(v6)

### 安装

```shell
yarn add react-router-dom
npm install -save react-router-dom
```

### 代码

```js
// 路由配置
<Router>
    <Routes>
        <Route path="/" element={<Home/>}/>
        <Route path="/user/mine" element={<Mine/>}/>
    </Routes>
</Router>
// 路由跳转
const navigate = useNavigate();
navigate('/home');
// 路由传参
navigate('/home?a=1&b=2');
// 取参
const [searchParams] = useSearchParams();
const a = searchParams.get("a");
const b = searchParams.get("b");
// 当前路径名
const location = useLocation();
const cpathname = location.pathname; 
```
## 打包
### 打包路径404问题
```react
package.json修改："homepage": "./",
```
