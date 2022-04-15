import React from "react";
import {Routes, Route, link, Navigate} from "react-router-dom"
import './App.css';
import { Home } from "./Components/Home";
import { Login } from "./Components/Login";
import { TodosCreate } from "./Components/TodosCreate";

const PrivateRoute = ({isAuthenticated, children}) => {
  return isAuthenticated ? children : <Navigate to="/login" />
}

function App() {

  const isAuthenticated = true

  const [count, setCount] = useState(0)
  return (
    <div className="App">
      <div>
        {/* <Routes>
          <Route path="/login" element={<Login />}></Route>
          <Route 
            path="/" 
            element={
              <PrivateRoute isAuthenticated={isAuthenticated}>
                <Home />
              </PrivateRoute>
          }></Route>
          <Route
           path="/todos-create" 
           element={
            <PrivateRoute isAuthenticated={isAuthenticated}>
              <TodosCreate />
            </PrivateRoute>
           }></Route>

        </Routes> */}

      </div>
    </div>
  );
}

export default App;
