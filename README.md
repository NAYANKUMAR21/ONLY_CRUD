# ONLY_CRUD
ONLY_CRUD
```bash
async function addpost(){
    let id = document.getElementById('id').value;
   let title = document.getElementById('title').value;
    let author = document.getElementById('author').value;

    let send_data={
        id,
        title,
        author
    }
    let res = await fetch(`http://localhost:3000/posts`,{
        method:'POST',
        body: JSON.stringify(send_data),
        headers:{
            'Content-Type':'application/json'
        },


    })
    let data=await res.json()
    console.log(data)
}

async function deletepost(){
    let id = document.getElementById('delete_id').value;
    let res=await fetch(`http://localhost:3000/posts/${id}`,{
        method:'DELETE',
        headers:{
            'Content-Type':'application/json'
        },
    })
    let data=await res.json()
    console.log(data)

}

let updatepost=async ()=>{
    const id = document.getElementById('update_id').value;
    const title = document.getElementById('update_title').value;
    let senddata={
        title
    }
    let res=await fetch(`http://localhost:3000/posts/${id}`,{
        method:'PATCH',
        body:JSON.stringify(senddata),
        headers:{
            'Content-Type':'application/json'
        }
    })
    let data=await res.json();
    console.log(data)
}
let replacepost = async ()=>{
    const id = document.getElementById('replace_id').value;
    const title = document.getElementById('replace_title').value;
    let senddata={
        title
    }
    let res=await fetch(`http://localhost:3000/posts/${id}`,{
        method:'PUT',
        body:JSON.stringify(senddata),
        headers:{
            'Content-Type':'application/json'
        }
    })
    let data=await res.json();
    console.log(data)
}
```
