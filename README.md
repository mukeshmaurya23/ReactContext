# ReactContext<div id="top"></div>
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->



<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->




<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/othneildrew/Best-README-Template">
    
  </a>

  <h3 align="center">Best-README-Template</h3>

  <p align="center">
    An awesome README template to jumpstart your projects!
    <br />
    <a href="https://github.com/othneildrew/Best-README-Template"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/othneildrew/Best-README-Template">View Demo</a>
    ·
    <a href="https://github.com/othneildrew/Best-README-Template/issues">Report Bug</a>
    ·
    <a href="https://github.com/othneildrew/Best-README-Template/issues">Request Feature</a>
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
   
    import React, { useState } from "react";
const AuthContext = React.createContext({
  token: "",
  isLoggedIn: false,
  login: (token) => {},
  logout: () => {},
});

/*here React.createContext({}) take an object and define the state which you want to access in context

**********************************************************************************************************
just like  Redux -->createSlice({
    const authInitialState = { isAuthenticated: false };
    const authSlice = createSlice({
            name: "authentication",
            initialState: authInitialState,
            reducers: {
             login(state) {
                state.isAuthenticated = true;
                },
            logout(state) {
                 state.isAuthenticated = false;
             },
  },
});
export const authActions = authSlice.actions;
export default authSlice.reducer;
    
******************************************************************************************************

now define a AuthContextProvider and object that define all Values and return a Provider with {props.children}

step:go on -->index.js and wrap it with AuthContextProvide which is name export{}
step:now use whenwhere you want to use it
eg import {useContext} from 'react;
   import AuthContext from '.../store
   const authCtx=useContext(AuthContext)
   and use component example
   authCtx.login(data.property)

*/

export const AuthContextProvider = (props) => {
  const [token, setToken] = useState(null);

  const userLoggedIn = !!token;
  const loginHandler = (token) => {
    setToken(true);
  };
  const logoutHandler = () => {
    setToken(null);
  };

  const authContext = {
    login: loginHandler,
    logout: logoutHandler,
    isLoggedIn: userLoggedIn,
    token: token,
  };
  return (
    <AuthContext.Provider value={authContext}>
      {props.children}
    </AuthContext.Provider>
  );
};
export default AuthContext;

   
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project



<p align="right">(<a href="#top">back to top</a>)</p>



### Built With

* [React.js](https://reactjs.org/)


<p align="right">(<a href="#top">back to top</a>)</p>



<!-- GETTING STARTED -->
## Getting Started

This is an example of how you may give instructions on setting up your project locally.
To get a local copy up and running follow these simple example steps.


