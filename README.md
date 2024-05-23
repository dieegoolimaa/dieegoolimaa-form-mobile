# React Native Form Example

This is a simple React Native application that demonstrates how to create a form using Formik and basic React Native components.

## Table of Contents
- [Overview](#overview)
- [Installation](#installation)
- [Usage](#usage)
- [Code](#code)
- [License](#license)

## Overview
This application features a basic form with several input fields to collect user information, including email, password, and details about a pet. It uses Formik for form handling and React Native components for the UI.

## Installation
To run this project locally, follow these steps:

1. **Clone the repository:**
   ```sh
   git clone https://github.com/your-username/react-native-form-example.git
   cd react-native-form-example
   ```

2. **Install dependencies:**
   ```sh
   npm install
   ```

3. **Run the application:**
   ```sh
   npm start
   ```

## Usage
Once the application is running, you can use the form to input your email, password, and pet information. Each input field is controlled by state variables managed by React's `useState` hook.

## Code
Here is the main code for the application:

```javascript
import React, { useState } from "react";
import { View, Text, TextInput, ScrollView } from "react-native";
import { Formik } from "formik";

const FormInput = ({ label, placeholder, value, onChangeText }) => {
  return (
    <View>
      <Text style={{ fontWeight: "bold", margin: 5 }}>{label}</Text>
      <TextInput
        placeholder={placeholder}
        value={value}
        onChangeText={onChangeText}
        style={{
          borderWidth: 1,
          borderColor: "gray",
          padding: 10,
          borderRadius: 5,
        }}
      />
    </View>
  );
};

const App = () => {
  const [email, setEmail] = useState("");
  const [password, setPassword] = useState("");
  const [petName, setPetName] = useState("");
  const [petDOB, setPetDOB] = useState("");
  const [breed, setBreed] = useState("");
  const [favoriteToy, setFavoriteToy] = useState("");

  return (
    <View
      style={{
        flex: 1,
        justifyContent: "center",
        backgroundColor: "#ecf0f1",
        padding: 20,
        marginTop: 50,
      }}
    >
      <Formik>
        <ScrollView>
          <FormInput
            label="Email:"
            placeholder="Enter your email"
            value={email}
            onChangeText={setEmail}
          />
          <FormInput
            label="Password:"
            placeholder="Enter your password"
            value={password}
            onChangeText={setPassword}
            secureTextEntry={true}
          />
          <FormInput
            label="Pet's Name:"
            placeholder="Enter your pet's name"
            value={petName}
            onChangeText={setPetName}
          />
          <FormInput
            label="Pet's Date of Birth:"
            placeholder="Enter your pet's date of birth"
            value={petDOB}
            onChangeText={setPetDOB}
          />
          <FormInput
            label="Breed:"
            placeholder="Enter your pet's breed"
            value={breed}
            onChangeText={setBreed}
          />
          <FormInput
            label="Favorite Toy:"
            placeholder="Enter your pet's favorite toy"
            value={favoriteToy}
            onChangeText={setFavoriteToy}
          />
        </ScrollView>
      </Formik>
    </View>
  );
};

export default App;
```

## License
This project is licensed under the MIT License. See the LICENSE file for more information.
