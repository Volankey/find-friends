# 描述
模仿qq颜值配对

右滑动为喜欢

左滑动为不喜欢


![image](./show.gif)
## Props

Name | type | arguments | desc
---|---|---|---
moveRight | Func | index number| 右滑动结束回调
moveLeft | Func | index number|左滑动结束回调
data | Array [src:"",sign:"",name:""]||列表数据
visibleNum | Number  | |能显示的卡片个数,需要小于data.length

## 使用示例

```
import LikeOrDiss from './compoents/LikeOrDiss/LikeOrDiss';
class App extends Component {
    constructor(props){
        super(props);

        this.state = {
            data:[]
        }

    }
    componentDidMount(){
        this.setState({
            data:[
                {src:require('./imgs/2.jpg'),sign:"寻找张无忌",name:"周芷若"},
                {src:'https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=1871526827,46354526&fm=27&gp=0.jpg',sign:"杀光所有坏人",name:"大表姐"},
                {src:require('./imgs/3.jpg'),sign:"hello world",name:"小姐姐"},
                {src:'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1521382896670&di=f094b281746d72bdd4e0d757f0346830&imgtype=0&src=http%3A%2F%2Ftvax1.sinaimg.cn%2Fcrop.0.0.1080.1080.1024%2F006RKM5sly8fgwmaicn1mj30u00u00ux.jpg',sign:" 我爱歌唱",name:"冯提莫"}
            ]
        })
    }
      render() {
        return (
            <LikeOrDiss
                moveRight={(idx)=>{alert("您喜欢了 "+this.state.data[idx].name)}}
                moveLeft={(idx)=>{alert("不喜欢 "+this.state.data[idx].name)}}
                visibleNum={3}
                data={this.state.data}
            />
        );
      }
}
```


