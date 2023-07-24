# NMAP

Nesse repositório irei abordar os comandos do nmap e uma exploração de como funciona essa ferramenta de reconhecimento na rede.
Muito valiosa para um ataque, pois a mesma possibilita você reconhecer o terreno da infraestrutura que você está atacando, quais os Sistemas operacionais de cada Host e quais vulnerabilidades os mesmo possuem.
Após "varrer" a infraestrutura do defensor é necessário organizar quais serão os alvos, e quais os ataques que podem ser projetados apara esses alvos. 



Se você conhece o inimigo e conhece a si mesmo, não precisa temer o resultado de cem batalhas. -Sun Tzu 

fping -g 192.168.0.100/24 2>/dev/null | grep "is alive" 
#Esse comando ira realizar uma verificação de quais hosts estão ativos na rede 
puxando do 192.168.0.1 ao 192.168.0.254 e os que estiverem ativos ele exibirar uma mensagem "is alive" (está vivo)

-nmap -sV -p 21,22,23,80,139,445, 192.168.0.1 
 Esse comando indetifica qual é o fabricante do dispositivo e quais portas estão abertas e seus respectivos serviços 

nmap -Pn 192.168.0.1 -top-ports=100
#Esse comando ira identifcar quais são as principais portas baseada nas 100 mais utilizadas e irá retornar se estão abertas ou fechadas 

-nmap -sV -p 21,22,23,80,139,445, -O 192.168.0.1 
#Esse comando serve para identificar o SO(Sistema Operacional) do host e ajuda identificar quais portas estão abertas nele também. 

nmap --script "vuln" -p 21,22,23,80,139,445  192.168.0.1
#Nesse comando será executado um script para encontrar uma vulnerabilidade para aquele host a vulnerabilidade sera exibida como CVE geralmente é composta de oito digitos separados Exemplo: CVE-2011-1002 DoS 

