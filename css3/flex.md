## flex 合法写法

```
flex: auto;
flex: none;
/* 1个值，flex-grow */
flex: 1;
/* 1个值，flex-basis */
flex: 100px;
/* 2个值，flex-grow和flex-basis */
flex: 1 100px;
/* 2个值，flex-grow和flex-shrink */
flex: 1 1;
/* 3个值，flex-grow和flex-shrink和flex-basis */
flex: 1 1 100px;
```

- initial

```
flex: initial;
<=>
flex: flex: 0 1 auto;
```

- auto

```
flex: auto;
<=>
flex: 1;
<=>
flex: 1 1 auto;
```

- none

```
flex: none;
<=>
flex: 0 0 auto;
```
