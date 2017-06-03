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
    
    let lastIndex= this.length-1
    let val= this.memory[lastIndex]
    
    delete this.memory[lastIndex]
    this.length--
    
    return val
}

shift(){
    if(this.length === 0) return;  //如果是空的就什麼都不做
    
    let val= this.memory[0]
    
    for(let Index=0; Index < this.length; Index++){
        this.memory[Index] = this.memory[Index+1]
    }
    
    delete this.memory[0]
    this.length--
    
    return val
}


unshift(val){
    let prev= val
    
    for(let Index=0; Index< this.length; Index++){
        let current= this.memory[Index]
        this.memory[Index] =prev
        prev=current
    }
    
    this.memory[this.length]= prev
    this.length++;
    
    
}

