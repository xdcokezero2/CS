import React, { useState } from "react";
import {
  StyleSheet,
  Text,
  ScrollView,
  Image,
  TextInput,
  Button,
  TouchableOpacity,
  Alert,
  View,
} from "react-native";
import { NavigationContainer} from '@react-navigation/native';
import { createStackNavigator } from "@react-navigation/stack";
import Login from "./Login";

const Stack = createStackNavigator();
function App(){
  return(
    <NavigationContainer>
      <Stack.Navigator>
      <Stack.Screen
      name="Login"
      component={Login}
      />
      <Stack.Screen
      name="HomeScreen"
      component={HomeScreen}
      />
      <Stack.Screen
      name="MechadoRecipe"
      component={MechadoRecipe}
      />
      <Stack.Screen
      name="ScrambledEggsRecipe"
      component={ScrambledEggsRecipe}
      />
      <Stack.Screen
      name="Friends"
      component={Friends}
      />
      <Stack.Screen
      name="Need Help?"
      component={NeedHelp}
      />
      </Stack.Navigator>
    </NavigationContainer>
    
    
  )
}
function HomeScreen({navigation}) {
  const gotomechado = () => {
    navigation.navigate('MechadoRecipe')
  }
  const ScrambledEggsRecipe = () => {
    navigation.navigate('ScrambledEggsRecipe')
  }
  const Friends = () => {
    navigation.navigate('Friends')
  }
  const NeedHelp = () => {
    navigation.navigate('Need Help?')
  }
  return (
    <ScrollView contentContainerStyle={{
      flexDirection: 'column',
      justifyContent: 'center',
      alignItems:'center'}}>
      <Image style={styles.mainImage}
      source={{
         uri: "https://www.lutongbahayrecipe.com/wp-content/uploads/2019/02/lutong-bahay-recipe-pork-mechado-2-678x381.jpg",}}
         />
               <Text style={styles.mainTitle}>Beef Mechado</Text>
            <TouchableOpacity
            onPress={gotomechado} 
            style={styles.cookBtn}>
        <Text style={styles.loginText}>START COOKING</Text>
      </TouchableOpacity>
      <Image style={styles.mainImage}
      source={{
         uri: "https://www.jessicagavin.com/wp-content/uploads/2020/09/how-to-make-scrambled-eggs-hard-7-600x900.jpg",}}
         />
               <Text style={styles.mainTitle}>Fluffy Scrambled Eggs</Text>
            <TouchableOpacity
            onPress={ScrambledEggsRecipe} 
            style={styles.cookBtn}>
        <Text style={styles.loginText}>START COOKING</Text>
      </TouchableOpacity>
      <View style={{flexDirection: 'row'}}>
      <TouchableOpacity
            onPress={NeedHelp} 
            style={styles.bottomBtn}>
        <Text style={styles.bottomText}>Need Help?</Text>
      </TouchableOpacity>
      <TouchableOpacity
            onPress={Friends} 
            style={styles.bottomBtn}>
        <Text style={styles.bottomText}>Friends</Text>
      </TouchableOpacity>
      </View>   
    </ScrollView>
    


    
    
  );
}
function MechadoRecipe() {
  return (
    <ScrollView contentContainerStyle={{
      flexDirection: 'column',
      alignItems:'center'}}>
         <Image style={styles.mainImage}
      source={{
         uri: "https://www.lutongbahayrecipe.com/wp-content/uploads/2019/02/lutong-bahay-recipe-pork-mechado-2-678x381.jpg",}}
         />
        <Text style={styles.recipeText}>
        Ingredients:{"\n"}</Text>
        <Text>
        1. 3 tablespoons cooking oil{"\n"}
        2. 1/2 kilo red onion, chopped{"\n"}
        3. 4 cloves garlic, mined{"\n"}
        4. 1 kilo beef, (use brisket), cut into large chunks{"\n"}
        5. 2 cups tomato sauce{"\n"}
        6. 1/2 cup soy sauce{"\n"}
        7. 2 cups beef stock{"\n"}
        8. 3 potatoes, quartered{"\n"}
        9. 1 carrot, cut into 1-inch chunks{"\n"}
        10. 2 bell pepper, sliced{"\n"}
        11. salt, to taste{"\n"}{"\n"}{"\n"}</Text>
        <Text style={styles.recipeText}>Cooking Procedure:{"\n"}</Text>
        <Text>
        1. Heat cooking oil in a pot then sauté the onion and garlic.{"\n"}
        2. Add the beef and sauté until lightly browned.{"\n"}
        3. Pour in the tomato sauce, soy sauce, beef stock and let it boil for a few minutes.{"\n"}
        4. Cover and continue to simmer everything over low heat until the beef is tender, {"\n"}
        approximately 1 hour. Check the pot from time to time if you need to add more stock or water.{"\n"}
        5. Once the beef is tender, add in the potatoes, carrots and cook for about 10 minutes.{"\n"}
        6. Add the bell pepper and cook for about 5 minutes just before serving.{"\n"}
        </Text>

    </ScrollView>
  );
}
function ScrambledEggsRecipe() {
  return (
    <ScrollView contentContainerStyle={{
      flexDirection: 'column',
      justifyContent: 'center',
      alignItems:'center'}}>
        <Image style={styles.mainImage}
      source={{
         uri: "https://www.jessicagavin.com/wp-content/uploads/2020/09/how-to-make-scrambled-eggs-hard-7-600x900.jpg",}}
         />
          <Text style={styles.recipeText}>
          Ingredients:{"\n"}</Text>
            <Text>
          1. 2 eggs{"\n"}
          2. Salt and Pepper to taste{"\n"}
          3.  tbsp. of butter{"\n"}
            </Text>
          <Text style={styles.recipeText}>Cooking Procedure:{"\n"}</Text>
        <Text>
        1. Whisk eggs, salt and pepper in small bowl. Melt butter in non-stick skillet over medium heat.{"\n"}
        2. Pour in egg mixture and reduce heat to medium-low. As eggs begin to set, gently move spatula across bottom and side of skillet to form large, soft curds.{"\n"}
        3. Cook until eggs are thickened and no visible liquid egg remains, but the eggs are not dry.{"\n"}
        </Text>
    </ScrollView>
    
  );
}
function Friends() {
  return (
    <ScrollView contentContainerStyle={{
      flexDirection: 'column',
      justifyContent: 'center',
      alignItems:'center'}}>
        <Image style={styles.mainImage}
      source={{
         uri: "https://i0.wp.com/www.sammichespsychmeds.com/wp-content/uploads/2017/12/Screen-Shot-2017-12-03-at-1.23.33-PM.png?fit=800%2C461&ssl=1",}}
         />
         <Text styles={styles.loginText}>
           You don't seem to have any friends.
         </Text>
    </ScrollView> 
  );
}
function NeedHelp() {
  return (
    <ScrollView contentContainerStyle={{
      flexDirection: 'column',
      justifyContent: 'center',
      alignItems:'center'}}>
        <Image style={styles.mainImage}
      source={{
         uri: "https://image.shutterstock.com/image-vector/male-hand-holding-megaphone-need-260nw-1627558870.jpg",}}
         />
         <Text styles={styles.loginText}>
           Contact us: {"\n"}
           Email us:Techsupport123@yahoo.com{"\n"}
           Mobile #: 0956 163 3455{"\n"}
           Landline #: 546 8910
         </Text>
    </ScrollView>
  );
}



const styles = StyleSheet.create({
  container: {
    backgroundColor: '#fff',
    flex: 1,
    flexDirection: 'column',
    justifyContent: 'center',
  },
  recipeText: {
    textAlign: 'left',
    fontWeight: 'bold',
    fontSize: 30,
  },
  loginText: {
    fontSize: 30,
  },
  bottomText: {
    fontSize: 10,
    fontWeight: 'bold',
  },
  mainImage: {
    marginBottom: 10,
    marginTop: 100,
    height: 400,
    width: 300,
  },
  mainTitle:{
fontSize: 30,
fontStyle: 'italic',
  },
  cookBtn: {
    width: "80%",
    borderRadius: 25,
    height: 50,
    alignItems: "center",
    justifyContent: "center",
    marginTop: 10,
    backgroundColor: "#FFFF00",
  },
  bottomBtn: {
    width: "20%",
    borderRadius: 25,
    height: 50,
    alignItems: "center",
    justifyContent: "center",
    marginTop: 10,
    backgroundColor: "#00FF00",
    marginHorizontal: 10,
  },
  loginBtn: {
    width: "80%",
    borderRadius: 25,
    height: 50,
    alignItems: "center",
    justifyContent: "center",
    marginTop: 40,
    backgroundColor: "#FF1493",
  },
  inputView: {
    backgroundColor: "#FFC0CB",
    borderRadius: 30,
    width: "70%",
    height: 45,
    marginBottom: 20,
  },
  forgot_button: {
    height: 30,
    marginBottom: 30,
    justifyContent: 'center',
  },
  menuBtn: {
    width: "10%",
    borderRadius: 25,
    height: 50,
    alignItems: "center",
    justifyContent: "center",
    marginTop: 10,
    backgroundColor: "#008080",
  },
});

export default App;
