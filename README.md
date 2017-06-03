# JSDataStructure

>list <br/>
>A list is a representation of an ordered sequence of value where the same value may appear many times.

    constructor(){
        this.memory=[]
        this.length=0
        //製作容器
    }

    get(Address){
        return this.memory[Address];
        //從list之中取資料且因為是有序的就直接使用索引取出
    }

    push(val){
        this.length++
        this.memory[this.length] = val
        //在這裡的重點是因為this.length與array索引不同的地方是從 1 開始, 所以會直接指向還未存在的最後一個指向
        //例如: [1,2,3,4] this.length=4 但是如果this[4]就是要push的val
    }

    pop(){
        if(this.length === 0) return;  //如果是空的就什麼都不做

        let lastIndex= this.length-1 //  [a,b,c,d] lastIndex為3
        let val= this.memory[lastIndex]  //val= this.memory[lastIndex]為 d

        delete this.memory[lastIndex] // 刪除以最後一個數字為索引的值 //刪除d
        this.length--  //長度減一

        return val //返回d
     }

    shift(){
        if(this.length === 0) return;  //如果是空的就什麼都不做

        let val= this.memory[0]  //val等於第一個元素 [a,b,c,d] ->a

        for(let Index=0; Index < this.length; Index++){
            this.memory[Index] = this.memory[Index+1] //以索引值+1取代原本的索引 [b,c,d]]
        }

        delete this.memory[0] //刪除頭
        this.length--  //長度減一

        return val
    }


    unshift(val){
        let prev= val  //例 [a,b,c,d] 要在頭部插入 val= x --> [x,a,b,c,d]

        for(let Index=0; Index< this.length; Index++){ //遍歷這個數組
            let current= this.memory[Index] //先以current當容器代表
            this.memory[Index] =prev // 解釋第一次遍歷, this.memory[0] = x 換句話說是用x 取代了this.memory[0] 也就是原本的a
                                             二        this.memory[1] = a            a(prev)                          b 
            prev=current //用current 取代prev
        }

        this.memory[this.length]= prev //this.memory[4] 代表第五個元素為剛剛遍歷完的最後一個prev 也就是d
        this.length++; // 長度加一

    }

