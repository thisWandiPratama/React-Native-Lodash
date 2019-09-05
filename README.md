# React-Native-Lodash

## Materi

 `Lodash` adalah `third-part-library` yang didalamnya berisi `function-function` yang digunakan untuk memanipulasi ragam tipe data

 ### Instalasi Lodash 

 intalasi `lodash` dilakukan didalam project React Native
 ```
~/home/project-rn $ npm install --save lodash
 ``` 

 ### Menggunakan Lodash 
 ```javascript
 import _ from 'lodash'
 ```

 contoh
 ```javascript
 import React from "react"
import { View, Text, TextInput, FlatList } from 'react-native'
import _ from 'lodash'

class Lodas extends React.Component {
    state = {
        text: [],
        data: [
            {
                nama: 'hafif'
            },
            {
                nama: 'Rifki'
            },
            {
                nama: 'dayat'
            },
            {
                nama: 'miko'
            },
            {
                nama: 'yusup'
            }]
    }
    test = () => {
        if (_.isEmpty(this.state.text)) {
            alert('data ini kosong')
        }
        else {
            alert('data ini ada')
        }
    }
    renderItems = ({ item, index }) => {
        const {nama}=item
        return(
            <Text>{nama}</Text>
        )
    }
    render() {
        return (
            <View>
                <FlatList
                    data={_.take(this.state.data,2)}
                    keyExtractor={item => item.toString()}
                    renderItem={this.renderItems} />
                <Text onPress={() => this.test()}>TEST</Text>
            </View>
        )
    }
}
export default Lodas
 ``` 


