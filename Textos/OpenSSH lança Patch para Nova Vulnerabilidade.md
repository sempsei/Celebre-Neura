Os responsáveis pela manutenção do OpenSSH lançaram o OpenSSH 9.2 para resolver uma série de bugs de segurança, incluindo uma vulnerabilidade de segurança de memória no servidor OpenSSH (sshd).

Rastreado como [CVE-2023–25136](https://nvd.nist.gov/vuln/detail/CVE-2023-25136), a falha foi classificada como uma vulnerabilidade de pré-autenticação dupla livre que foi introduzida na versão 9.1.

“Não se acredita que isto seja explorável, e ocorre no processo de pré-autenticação sem privilégios que está sujeito a chroot(2) e que é ainda mais “sandbox” na maioria das principais plataformas”, OpenSSH revelou nas suas notas de lançamento a 2 de Fevereiro de 2023.

Creditado com a denúncia da falha à OpenSSH em Julho de 2022 é o investigador de segurança Mantas Mikulenas.

OpenSSH é a implementação de código aberto do protocolo secure shell (SSH) que oferece um conjunto de serviços para comunicações codificadas através de uma rede não segura numa arquitetura cliente-servidor.

“A exposição ocorre no pedaço de memória libertado duas vezes, o ‘options.kex_algorithms’”, disse o investigador Qualys Saeed Abbasi, acrescentando que a questão resulta num “duplo livre no processo sshd não-privilegiado”.

Duplas falhas livres surgem quando um pedaço vulnerável de código chama a função free() — que é utilizada para desalocar blocos de memória — duas vezes, levando à corrupção da memória, o que, por sua vez, poderia levar a uma falha ou execução de código arbitrário.

“A memória duplamente livre pode resultar numa condição de escrita-o-quê, permitindo que um atacante execute um código arbitrário”, observa MITRE na sua descrição da falha.

“Embora a dupla vulnerabilidade livre no OpenSSH versão 9.1 possa levantar preocupações, é essencial notar que a exploração desta questão não é uma tarefa simples”, explicou Abbasi.

“Isto deve-se às medidas de proteção postas em prática pelos modernos alocadores de memória e à robusta separação de privilégios e sandboxing implementados no processo sshd impactado”.

Recomenda-se aos utilizadores que atualizem o OpenSSH 9.2 para mitigar potenciais ameaças à segurança.

Fonte: [https://thehackernews.com/2023/02/openssh-releases-patch-for-new-pre-auth.html](https://thehackernews.com/2023/02/openssh-releases-patch-for-new-pre-auth.html)