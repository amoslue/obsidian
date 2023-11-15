# 30 Days of React: Props

![rw-book-cover](https://opengraph.githubassets.com/971d7ed7ba99a3184e6e678f878bd58258ca8960d4b826368619f5bcf5354b32/amoslue/30-Days-Of-React)

## Metadata
- Author: [[GitHub]]
- Full Title: 30 Days of React: Props
- Category: #articles
- URL: https://github.com/amoslue/30-Days-Of-React/blob/master/05_Day_Props/05_props.md

## Highlights
- Props is a special keyword in React that stands for properties and is being used to pass data from one component to another and mostly from parent component to child component. We can say props is a data carrier or a means to transport data. ([View Highlight](https://read.readwise.io/read/01hf96p3gmdx1tvxb4477jadcn))
- // User component, component should start with an uppercase const User = (props) => { return ( <div> <h1> {props.firstName} {props.lastName} </h1> <small>{props.country}</small> </div> ) } // calling or instantiating a component, this component has three properties and we call them props:firstName, lastName, country <User firstName = 'Asabeneh', lastName='Yetayeh' country = 'Finland' /> ([View Highlight](https://read.readwise.io/read/01hf96r8593ta5pxth67ktz1db))
    - Note: props example
- // Header Component const Header = (props) => { console.log(props) // empty object, {} return ( <header> <div className='header-wrapper'> <h1>{welcome}</h1> <h2>{title}</h2> <h3>{subtitle}</h3> <p> {author.firstName} {author.lastName} </p> <small>{date}</small> </div> </header> ) } // The App, or the parent or the container component // Functional Component const App = () => { return ( <div className='app'> <Header /> </div> ) } ([View Highlight](https://read.readwise.io/read/01hf96w355z7cmz0cshw897ysz))
    - Note: use props to inject data
