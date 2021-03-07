### react 기본 형식
```
    class GuGuDan extends React.Component{
        constructor(props){
            super(props);
            this.state = {

            };
        }
        render(){
           return;
        }
    }
```


#### 강의 8
- form이 들어가면 onSubmit을 쓴다.(제로초)
- form이 없으면 button에 onclick ={this.onSubmit}
- 직접 만들어 주는 함수둘은 무조건 화살표 함수를 쓰자 -> this가 변경되니까 변경되지 않도록

### 강의9
```
onSubmit = (e) => {
    e.preventDefault();
    if (parseInt(this.state.value) === this.state.first * this.state.second) {
        //setState에다가 바꾸고 싶은 상태를 입력하면된다.
        this.setState((prevState) => {
            return{
                result: '정답 : ' + prevState.value,
                first: Math.ceil(Math.random() * 9),
                second: Math.ceil(Math.random() * 9),
                value: '',
            };
        });

        this.setState({
            value: this.state.value + 1,
        });
        this.setState({
            value: this.state.value + 1,
        });
        this.setState({
            value: this.state.value + 1,
        });
        //새로운 value가 기존 value + 3 될거라고 예상을 한다. 하지만 value + 1이 될 수도 있다. 비동기이기 때문에
        //한가지 원칙으로 외워주자
        //예전 state로 새로운 state를 만들 때는 리턴해주는 함수를 쓰는 것으로 외우자!!
        this.setState((prevState) => {
            return{
                value: this.state.value + 1
            };
        });
    } else {
        this.setState({
            result: '땡',
            value: '',
        });
    }
};
```
- 예전 상태값을 `prevState.value`를 다음 상태값에 넣을 수 있을 때 명시적으로 확인이 편함

### 10
- 리액트가 화면을 만들어 준다고 생각하고 우리가 할 일은 데이터를 바꿔주는 것이다.