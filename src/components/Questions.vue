<template>
  <div>
    <img src="../assets/FonteAjudate.png" alt="LogoImg" >
  </div>
  <h1> {{perguntas[iPerguntas].text}} </h1>
  <h1> {{perguntas[iPerguntas].text2}} </h1>
  <div class="ScreenSize" >
    <div class="QuestionForm" >
      <div v-if='iPerguntas == 0' class="RadioForm">
        <el-radio class="RadioButton" v-model="radio1" label="Traje Esportivo" > Traje Esportivo 
          <span class="TooltipText" >
            <strong>Ocasião:</strong> Viagens, Compras, Clubes, Praia. <br><br>
            <strong>Ele:</strong> Camisa sem gravata, "Blazer" esportivo. Sapatos tipo mocassim, Jeans. <br><br>
            <strong>Ela:</strong> Calça comprida, Saia e blusa, Vestido tubo, Jeans.
          </span>
        </el-radio>
        <el-radio class="RadioButton" v-model="radio1" label="Traje Esportivo Fino" > Traje Esportivo Fino 
          <span class="TooltipText" >
            <strong>Ocasião:</strong> Teatros, Cinema, Almoços, Jantares íntimos. <br><br>
            <strong>Ele:</strong> Terno escuro, Gravata de seda. <br><br>
            <strong>Ela:</strong> Tailleur de calça ou saia, Vestido chemisier.
          </span>
        </el-radio>
        <el-radio class="RadioButton" style="font-size: medium;" v-model="radio1" label="Traje Passeio Completo ou Social" > Traje Passeio Completo ou Social 
          <span class="TooltipText" >
            <strong>Ocasião:</strong> Jantares, coquetéis, chás, casamento, óperas, desfiles. <br><br>
            <strong>Ele:</strong> Gravata, Terno único escuro, Camisa social, Sapatos pretos e gravata. <br><br>
            <strong>Ela:</strong> Tailleur, Pantalonas, Vestidos de bons tecidos como seda ou casimira.
          </span>
        </el-radio>
        <el-radio class="RadioButton" v-model="radio1" label="Traje Black-Tie ou Texudo" > Traje Black-Tie ou Texudo 
          <span class="TooltipText" >
            <strong>Ocasião:</strong> Formaturas, Casamentos, Jantares formais, Solenidades. <br><br>
            <strong>Ele:</strong> Smoking. <br><br>
            <strong>Ela:</strong> Roupas em brocados, Bordados, Casimira, Sedas, Rendas.
          </span>
        </el-radio>
        <el-radio class="RadioButton" v-model="radio1" label="Traje Gala ou Rigor" > Traje Gala ou Rigor 
          <span class="TooltipText" >
            <strong>Ocasião:</strong> Formaturas, Casamentos, Jantares formais, Solenidades. <br><br>
            <strong>Ele:</strong> Smoking. <br><br>
            <strong>Ela:</strong> Roupas em brocados, Bordados, Casimira, Sedas, Rendas.
          </span>
        </el-radio>
      </div>
      <div v-if='iPerguntas == 1' class="RadioForm">
        <el-radio class="RadioButton" v-model="radio2" label="Hambúrguer" > Hambúrger </el-radio>
        <span class="SpanInput" v-if='radio2 == "Hambúrguer"' ><strong class="InputTitle" >Restaurante :</strong> 
          <el-input class="InputText" v-model="input" size="mini" ></el-input>
        </span>
        <el-radio class="RadioButton" v-model="radio2" label="Comida Japonesa" > Comida Japonesa </el-radio>
        <span class="SpanInput" v-if='radio2 == "Comida Japonesa"' ><strong class="InputTitle" >Restaurante :</strong> 
          <el-input class="InputText" v-model="input" size="mini" ></el-input>
        </span>
        <el-radio class="RadioButton" v-model="radio2" label="Comida Mexicana" > Comida Mexicana </el-radio>
        <span class="SpanInput" v-if='radio2 == "Comida Mexicana"' ><strong class="InputTitle" >Restaurante :</strong> 
          <el-input class="InputText" v-model="input" size="mini" ></el-input>
        </span>
        <el-radio class="RadioButton" v-model="radio2" label="Comida Árabe" > Comida Árabe </el-radio>
        <span class="SpanInput" v-if='radio2 == "Comida Árabe"' ><strong class="InputTitle" >Restaurante :</strong> 
          <el-input class="InputText" v-model="input" size="mini" ></el-input>
        </span>
        <el-radio class="RadioButton" v-model="radio2" label="Massas e Molhos" > Massas e Molhos </el-radio>
        <span class="SpanInput" v-if='radio2 == "Massas e Molhos"' ><strong class="InputTitle" >Restaurante :</strong> 
          <el-input class="InputText" v-model="input" size="mini" ></el-input>
        </span>
        <el-radio class="RadioButton" v-model="radio2" label="Outros" > Outros </el-radio>
        <span class="SpanInput" v-if='radio2 == "Outros"' ><strong class="InputTitle" >Restaurante :</strong> 
          <el-input class="InputText" v-model="input" size="mini" ></el-input>
        </span>
      </div>
      <div v-if='iPerguntas == 2' class="RadioForm">
        <el-radio class="RadioButton" v-model="radio3" label="50" > R$50,00 </el-radio>
        <el-radio class="RadioButton" v-model="radio3" label="100" > R$100,00 </el-radio>
        <el-radio class="RadioButton" v-model="radio3" label="150" > R$150,00 </el-radio>
        <el-radio class="RadioButton" v-model="radio3" label="200" > R$200,00 </el-radio>
        <el-radio class="RadioButton" v-model="radio3" label="Outros Valores" > Outros Valores 
          <span class="TooltipTextValor" > Coloque somente o valor. Ex: 1000 </span>
        </el-radio>
        <span class="SpanInput" v-if='radio3 == "Outros Valores"' ><strong class="InputTitle" >Valor :</strong> 
          <el-input class="InputText" v-model="value" size="mini" ></el-input>
        </span>
      </div>
      <div v-if='iPerguntas == 3' class="RadioForm">
        <el-radio class="RadioButton" v-model="radio4" label="Sim! Lógico!" > Sim! Lógico! </el-radio>
        <el-radio class="RadioButton" v-model="radio4" label="'Magina', a gente pode se encontrar la" > "Magina", a gente pode se encontrar la </el-radio>
        <el-radio class="RadioButton" v-model="radio4" label="Ah, pra mim não faz diferença..." > Ah, pra mim não faz diferença... </el-radio>
        <el-radio class="RadioButton" v-model="radio4" label="Não, eu consigo ir sozinho(a)" > Não, eu consigo ir sozinho(a) </el-radio>
      </div>
      <div v-if='iPerguntas == 4' class="RadioForm">
        <div class="Terms" >
          <span>
            Nosso serviço proporciona os melhores dates através de um algoritmo especializado, o mesmo busca refinar entre os melhores candidatos para assim seu melhor proveito. <br><br>
            Garantimos o seu total aproveitamento, caso o contrário disponibilizamos um reembolso e grátis um mês de assinatura para garantir que ha esperança pra seu date perfeito. <br><br>
            Ao aceitar os termos o algoritmo irá automaticamente selecionar seu date perfeito e confirmar todas as suas escolhas para que não tenha absolutamente nenhum erro dentro de todo o processo. A partir desse momento, o date vai estar em suas mãos.
          </span>
          <el-checkbox class="CheckBox" v-model="checked" label="termos" > Li e aceito os Termos e Condições </el-checkbox>
        </div>
      </div>
      <div v-if='iPerguntas == 5' class="SummForm">
        <div class="Summ" >
          <div class="LandingPageLogo"  @click="startApp" >
              <img class="LogoAjudate" max-height="756" max-width="536" src="../assets/LogoCompleto.png" alt="LogoAjudate" />
          </div>
          <div class="SummObj" >
            <p><strong> Date Perfeito : </strong> Vitor Lazaretti de Sá </p>
            <p><strong> Traje Escolhido : </strong> {{radio1}} </p>
            <p><strong> Local Escolhido : </strong> {{input}} </p>
            <p v-if='radio3 == "Outros Valores" ' ><strong> Valor Escolhido : </strong> R${{value}},00 </p>
            <p v-if='radio3 != "Outros Valores" ' ><strong> Valor Escolhido : </strong> R${{radio3}},00 </p>
            <p><strong> Carona : </strong> {{radio4}} </p>
          </div>
        </div>
      </div>
      <div class="FinalForm" v-if='iPerguntas == 5' >
        <p> Você gostaria de ir nesse date como a minha namorada? </p>
        <h3>PS: Sim, estou te pedindo em namoro AGORA!</h3>
        <div class="FinalFormBtns">
          <div>
            <el-button class="FinalButtons" type="primary" size="small" style="color: #707070; background-color: #71D4DA; border: none" @click="yesModal" > SIM </el-button>
          </div>
          <div>
            <el-button class="FinalButtons" type="primary" size="small" style="color: #707070; background-color: #71D4DA; border: none" @click="noModal" > NÃO </el-button>
          </div>
        </div>
      </div>
      <div class="ButtonForm">
        <div>
          <el-button class="FormButtons" type="primary" size="small" style="color: #707070; background-color: #AD96E4; border: none" @click="voltarPergunta" > Voltar </el-button>
        </div>
        <div>
          <el-button v-if="iPerguntas != 5" class="FormButtons" type="primary" size="small" style="color: #707070; background-color: #AD96E4; border: none" @click="proximaPergunta" > Próximo </el-button>
        </div>
      </div>
    </div>
    <div class="ScreenImages" >
      <img class="TelaTraje" v-if='iPerguntas == 0' max-height="756" max-width="536" src="../assets/TelaTraje.png" alt="TelaTraje" />
    </div>
    <div class="ScreenImages" >
      <img class="TelaComida" v-if='iPerguntas == 1' max-height="756" max-width="536" src="../assets/TelaComida.png" alt="TelaComida" />
    </div>
    <div class="ScreenImages" >
      <img class="TelaValores" v-if='iPerguntas == 2' max-height="756" max-width="536" src="../assets/TelaValores.png" alt="TelaValores" />
    </div>
    <div class="ScreenImages" >
      <img class="TelaCarona" v-if='iPerguntas == 3' max-height="756" max-width="536" src="../assets/TelaCarona1.png" alt="TelaCarona" />
    </div>
    <div class="ScreenImages" >
      <img class="TelaTermos" v-if='iPerguntas == 4' max-height="756" max-width="536" src="../assets/TelaTermosECondições.png" alt="TelaTermos" />
    </div>
    <div class="ScreenImages" >
      <img class="TelaFinalD" v-if='iPerguntas == 5' max-height="756" max-width="536" src="../assets/TelaConfirmaçãoDireita.png" alt="TelaFinalDireita" />
    </div>
    <div class="ScreenImagesE" >
      <img class="TelaFinalE" v-if='iPerguntas == 5' max-height="756" max-width="536" src="../assets/TelaConfirmaçãoEsquerda.png" alt="TelaFinalEsquerda" />
    </div>
  </div>
</template>

<script>
let questions = [
        {
          text: "Para começar, precisamos saber o que seria um date perfeito para você.",
          text2: "E que melhor jeito começar senão pelo traje? Qual seria o perfeito para o date?"
        },
        {
          text: "Agora que já decidimos o traje, que tal passarmos para a comida?",
          text2: "Qual é aquela comida que de trás os melhores momentos? E depois de escolher, porque não sugerir o restaurante?"
        },
        {
          text: "Ok, traje e restaurante escolhidos, o que mais falta?",
          text2: "Ah sim, falta saber o quanto seria apropriado gastar em um date assim, cada um possui o seu valor não é mesmo?"
        },
        {
          text: "Existe uma chance de você ter achado a última pergunta insensitiva.",
          text2: "Mas agora falando de sensibilidade, o seu Date perfeito deve passar na sua casa pra dar uma caroninha até o restaurante?"
        },
        {
          text: "Todas as perguntas respondidas, agora só precisa ler nossos termos e condições",
          text2: "Garantimos que vai ser algo bem rapidinho, então por favor confere para ver se está tudo certo!"
        },
        {
          text: "Pronto, agora chegamos na última etapa. Basta confirmar e esperar seu date.",
          text2: "Esperamos do fundo de nossos corações que você seja feliz acima de tudo"
        }
      ]

export default {
  name: "Questions",
  data() {
    return {
      perguntas: questions,
      iPerguntas: 0,
      radio1: "Traje Esportivo",
      radio2: "Hambúrguer",
      radio3: "50",
      radio4: "Sim! Lógico!",
      checked: false,
      input: "",
      value: "",
    }
  },
  mounted() {
    console.log(this.perguntas[0].text)
  },
  methods: {
    proximaPergunta() {
      if(this.iPerguntas < this.perguntas.length - 1) {
        this.iPerguntas++
      }
      else {
        console.log("Tá no máximo carai!")
      }
    },
    voltarPergunta() {
      if(this.iPerguntas > 0) {
        this.iPerguntas--
      }
      else {
        console.log("Já voltou tudo porra!")
      }
    },
    yesModal() {
      this.$alert(
        '<img src="https://media0.giphy.com/media/ir1FV4pWSmrXMfTNNY/giphy.gif?cid=ecf05e47cdwxu4wwzdtx9zwwzngq292q5r02z4vg27cmj3ht&rid=giphy.gif&ct=g" style="width: 370px;" width="450" height="auto" frameBorder="0" class="giphy-embed" allowFullScreen /><br><br><p style="color: green;" ><strong> EU TE AMO!!!! </strong></p>',
        "Você disse SIM!!!!!!!",
        {
          dangerouslyUseHTMLString: true,
          center: true,
        }
      )
    },
    noModal() {
      this.$alert(
        '<span style="color: red; font-size: 18px;" >Tente Novamente</span>',
        "Você disse NÃO???!!!",
        {
          dangerouslyUseHTMLString: true,
          cente: true
        }
      )
    },
    logRadioValue() {
      console.log(this.radio1)
      console.log(this.radio2)
      console.log(this.input)
      console.log(this.radio3)
      console.log(this.value)
      console.log(this.radio4)
    }
  }
}
</script>

<style scoped>
  img {
    height: 100px;
    width: auto;
    margin: -3%;
  }

  .LogoAjudate {
    height: 200px;
  }

  @font-face {
    font-family: CovesLight;
    src: url(../assets/fonts/CovesLight.otf);
  }
  
  h1 {
    font-family: CovesLight;
    font-size: 26px;
    color: #343434;
  }

  h3 {
    font-size: 12px;
  }

  span {
    font-family: CovesLight;
  }

  .QuestionForm {
    position: relative;
    height: 680px;
    width: 820px;
    background-color: #F79ECC;
    border-radius: 50px;
  }

  .ScreenSize {
    height: auto;
    width: auto;
    display: flex;
    justify-content: center;
  }

  .ButtonForm {
    position: absolute;
    display: flex;
    justify-content: space-between;
    left: 0;
    bottom: 0;
    margin-bottom: 1%;
    z-index: 2;
  }

  .FormButtons {
    margin-right: 320px;
    margin-left: 80px;
    max-height: 20px;
    width: 130px;
    border-radius: 10px;
    font-family: CovesLight;
    font-size: 16px;
    font-weight: bolder;
  }

  .RadioForm {
    display: grid;
    justify-content: center;
    margin-top: 35px;
  }

  .RadioButton {
    width: 300px;
    color: #707070;
    border-radius: 10px;
    background-color: #71D4DA;
    padding-left: 10px;
    margin: 25px;
    margin-top: 50px;
    margin-bottom: 0px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.1), 0 6px 20px 0 rgba(0, 0, 0, 0.1);
  }

  .RadioButton .TooltipText {
    display: block;
    visibility: hidden;
    width: 120px;
    background-color: #71D4DA;
    color: #707070;
    text-align: left;
    border-radius: 10px;
    padding: 5px 5px;
    top: -40px;
    left: 105%;
    font-size: 12px;
    word-wrap: break-word;
    white-space: normal;

    position: absolute;
    z-index: 1;
  }

  .RadioButton:hover .TooltipText {
    visibility: visible;
  }

  .RadioButton .TooltipText::after {
    content: " ";
    position: absolute;
    top: 50%;
    right: 100%; /* To the left of the tooltip */
    margin-top: -5px;
    border-width: 5px;
    border-style: solid;
    border-color: transparent #71D4DA transparent transparent;
  }

  .SpanInput {
    width: 300px;
    color: #707070;
    background: #71D4DA;
    margin: -7px 0px 0px 25px;
    font-size: 12px;
    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;
    display: flex;
    text-align: left;
    padding-left: 10px;
    padding-top: 10px;
  }
  
  .InputTitle {
    margin: 10px;
    margin-left: 14px;
  }

  .InputText {
    margin: 2px 0px 5px 0px;
    width: 200px;
  }

  .RadioButton .TooltipTextValor {
    display: block;
    visibility: hidden;
    width: 120px;
    background-color: #71D4DA;
    color: #707070;
    text-align: left;
    border-radius: 10px;
    padding: 5px 5px;
    top: 3px;
    left: 105%;
    font-size: 12px;
    word-wrap: break-word;
    white-space: normal;

    position: absolute;
    z-index: 1;
  }

  .RadioButton:hover .TooltipTextValor {
    visibility: visible;
  }

  .RadioButton .TooltipTextValor::after {
    content: " ";
    position: absolute;
    top: 50%;
    right: 100%; /* To the left of the tooltip */
    margin-top: -5px;
    border-width: 5px;
    border-style: solid;
    border-color: transparent #71D4DA transparent transparent;
  }

  .Terms {
    font-size: 30px;
    margin: 30px;
  }

  .CheckBox {
    width: 300px;
    color: #707070;
    border-radius: 10px;
    background-color: #71D4DA;
    padding-left: 10px;
    margin: 25px;
    margin-top: 30px;
    margin-bottom: 0px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.1), 0 6px 20px 0 rgba(0, 0, 0, 0.1);
  }

  .SummForm {
    display: grid;
    justify-content: center;
    margin-top: 35px;
  }


  .Summ {
    margin: 20px;
    font-family: CovesLight;
  }

  .SummObj {
    font-size: 18px;
    text-align: justify;
  }

  .FinalForm {
    margin-top: -20px;
    font-family: CovesLight;
    font-size: 19px;
    font-weight: bolder;
  }

  .FinalFormBtns {
    display: flex;
    justify-content: space-between;
    margin-left: 180px;
    margin-right: 180px;
    margin-top: 25px;
  }

  .FinalButtons {
    color: rgb(112, 112, 112);
    background-color: rgb(113, 212, 218);
    border: none;
    max-height: 20px;
    width: 130px;
    border-radius: 10px;
    font-family: CovesLight;
    font-size: 16px;
    font-weight: bolder;
  }

  .ScreenImages {
    height: auto;
    width: auto;
    position: absolute;
    bottom: 0px;
    right: 0px;
    overflow: hidden;
    padding: 25px;
  }

  .ScreenImagesE {
    height: auto;
    width: auto;
    position: absolute;
    bottom: 0px;
    left: 0px;
    overflow: hidden;
    padding: 25px;
  }

  .TelaTraje {
    height: 400px;
  }

  .TelaComida {
    height: 400px;
    margin-right: 10px;
  }

  .TelaValores {
    height: 400px;
  }

  .TelaCarona {
    height: 400px;
    margin-right: 200px;
  }

  .TelaTermos {
    height: 400px;
    margin-right: -60px;
  }

  .TelaFinalD {
    height: 300px;
  }

  .TelaFinalE {
    height: 350px;
  }

  /*
  .RadioInfo {
    width: 300px;
    color: #707070;
    background: #71D4DA;
    margin: -7px 0px 0px 25px;
    font-size: 9px;
    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;
    display: block;
    text-align: left;
    padding-left: 10px;
    padding-top: 10px;
  }*/

</style>