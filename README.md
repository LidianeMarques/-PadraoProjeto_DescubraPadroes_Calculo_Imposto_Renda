# <h1 align="center"> Padrões de Projeto </h1>
<hr/>

## <h2 align="center">DESCUBRA E APLIQUE PADRÕES </h2>

<div align="justify">
  
 ## <h2 align="center">Cálculo de Imposto de Renda </h2>
 
 <p>Considere um sistema de recursos humanos que possui uma hierarquia de classes de Pessoa, PessoaFisica (PF) e PessoaJuridica (PJ), sendo a 1ª a superclasse das 2 últimas.  O cálculo do imposto de renda (IR) para PF é diferente para PJ. Por simplificação, vamos considerar que PFs pagam 11% de alíquota de IR, seguindo a fórmula: </p>

  * IR (R$) = [(Salário bruto - dedução em R$ por dependente - R$ INSS) X alíquota IRPF] - (gastos saúde + gastos educação)
  
  <p>No caso de PJ existem diferentes cálculos. Vamos considerar apenas o cálculo para empresas que aderem ao regime tributário chamado "Lucro Real". Neste caso, elas pagam 15% sobre o lucro da companhia. Caso a empresa exceda R$ 20 mil por mês na cobrança de IR, ela também paga 10% sobre o valor que exceder.
  
A PF física paga INSS. Por simplificação, vamos considerar que são 11% sobre o salário bruto (com a reforma da previdência, existe uma ampla faixa de alíquotas). 

A PJ paga INSS para seus funcionários, mas não vamos considerar isto aqui. Considere a Contribuição Social sobre Lucro Líquido (CSLL) que, de forma simplificada, aqui consideraremos 9% do lucro.

Adicionalmente, a PJ paga ICMS por produtos adquiridos. Vamos considerar que a alíquota é de 5%.

</p>

<p>Resumindo:</p>
  * A PF paga IR + INSS
  * A PJ paga IR + CSLL + ICMS

Responda:

1. Considerando que deve-se garantir que o cálculo inclua o valor do IR, que padrão de projeto pode ser aplicado para isto?

ℹ️ Nota: Lembrando que não necessariamente o padrão precisa ser aplicado, pois podemos resolver de uma forma simples. Tudo depende do problema em questão. Considerando que existem diversas maneiras de calcular o IR para PJ e que precisaríamos trocar uma implementação pela outra de acordo com determinadas condições, isto justificaria a implementação de um padrão.

    <p>Ao meu ver, podemos aplicar uns três padõres diferentes, são: Strategy sozinho ou com Template Method. Por que segundo a aplicabilidade do padrão:</p>
      
    * Um comportamento de método(implementação de um algoritmo) precisa ser diferente em classes distintas e/ou <b> mudar em tempo de execução </b>;
    * Uma determinada classe deve ter comportamento específico (método) e outras não;
    * Não deseja-se que uma alteração em uma superclasse afete subclasses;
    
</div>
