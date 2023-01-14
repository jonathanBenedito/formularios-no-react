# Aula 05 - Formulários no React
📄 Link de acesso aos <a href="https://cord-delivery-7eb.notion.site/React-Avan-ado-0dd7bebfaf364c1f8544098923b060e5">resumos</a>. 

🖼 Link de <a href="https://glittery-travesseiro-cc25ad.netlify.app/">demonstração</a>.

- `onChange` → É um evento que executa uma função toda vez que seu valor for alterado, isso geralmente é utilizado em formulários para atualizar e registrar o valor do `input`.
- `onSubmit` → É um evento que executa uma função quando um usuário envia um formulário através do botão de `submit`, comumente usado com hooks.
```jsx
const Form = (props) => {

    const [inputs, setInputs] = useState({
        image: ''
    })

    const handleInputChange = (event) => {
        setInputs({
            image: event.target.value
        })
    }

    const handleSubmit = (event) => {
        event.preventDefault()
        props.addCard(inputs)
    }

    return (
        <>
            <form onSubmit={handleSubmit}>
                <div>
                    <label htmlFor='image'>Endereço da imagem da carta</label>
                    <input type="text" id="image" name="image" onChange={handleInputChange} value={inputs.image}/>
                </div>
                <input type="submit" />
            </form>
        </>
    )
}
```