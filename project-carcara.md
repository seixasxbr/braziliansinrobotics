---
layout: page
title: Carcara
subtitle: Um veículo aéreo não tripulado autônomo
---
{% assign date_format = site.date_format | default: "%B %-d, %Y" %}
{%- capture site_tags -%}
    {%- for tag in site.tags -%}
      {% if tag contains 'carcara' %}
        {{- tag | first -}}{%- unless forloop.last -%},{%- endunless -%}
      {% endif %} 
    {%- endfor -%}
{%- endcapture -%}
{%- assign tags_list = site_tags | split:',' | sort -%}

<center>
  <img src="{{ 'assets/img/carcara/CARCARAf.png' | relative_url }}" width="750" text-align=center alt="img1" />
</center>

<div class="before-content">
  <center>
    {%- for tag in tags_list -%}
      <a href="#{{- tag -}}" class="btn btn-primary tag-btn"><i class="fas fa-tag" aria-hidden="true"></i>&nbsp;{{- tag -}}-posts&nbsp;({{site.tags[tag].size}})</a>
    {%- endfor -%}
  </center>    
  <!--hr class="mark"-->
</div>

<!-- ## Introdução -->
O uso de veículos aéreos não tripulados tem se popularizado em diversas áreas, como agricultura, cinematografia, militar, entretenimento, inspeção e de entregas. Muitas dessas tarefas tem a necessidade da implementação de autonomia nesse tipo de plataforma. Nesse contexto, se iniciou o desenvolvimento do projeto Carcara, que envolve a concepção de um VANT do tipo quadrotor e a implementação da autonomia nele. O principal objetivo desse projeto é realizar o pouso autônomo dessa veículo em uma plataforma móvel, já que um dos grandes desafios do uso de drones é a sua baixa autonomia (tempo de vôo) e pode existir a necessidade dessa operação para ser realizada uma possível recarga da bateria. O veículo móvel que será usado para a realização do pouso é uma caminhonete modelo L200.

<center>
  <img src="{{ 'assets/img/carcara/objetivo4.png' | relative_url }}" width="750" text-align=center alt="img1" />
</center>
 

### DESIGN E CARACTERÍSTICAS

Existem duas principais configurações para quadrotores, sendo elas a configuração plus (+) ou a configuração cross (x). A configuração escolhida para o carcará foi a cross, devido ao menor consumo energético na translação para essa configuração, maior estabilidade e também pelo fato da configuração plus causar oclusão na câmera. O framework utilizado para gerenciar o Carcara é o ROS2 e sua modelagem foi desenvolvida no Onshape.

<center>
  <img src="{{ 'assets/img/carcara/carcarareal.jpg' | relative_url }}" width="750" text-align=center alt="img1" />
</center>

<br>

### TECNOLOGIA ENVOLVIDA

O Carcara conta com diversos sensores e tecnologias para auxiliar no seu funcionamento. Para o fornecimento de energia o Carcara conta com uma bateria LiPo de 500 mAh 60C 3S e uma Mini Power Hub Matek para distribuir a energia. Os motores dos propulsores são motores trifásicos Brushless do tipo X2212 de 13 kV 980 II e os controladores dos motores são ESC Racestar 30A. Os componentes responsáveis pela percepção são duas câmeras Raspberry Pi v2 de 8MP, uma orientada para a frente do robô e uma para baixo, 5 sensores ultrassônicos HC-SR04 para ajudar no desvio de obstáculos, um laser TOF10120 orientado para baixo para medir distância, uma IMU MPU-9250 e um barômetro MS5611. A unidade de processamento central é um Teensy 4.0 enquanto a unidade de processamento auxiliar é uma Jetson Nano Development Kit para processar redes neurais, processamento de imagem, etc. Para a funcionalidade de comunicação, ele possui um Radio Receiver FS-R6B e um adaptador WiFi AC600.

<center>
  <img src="{{ 'assets/img/carcara/exploded_with_transcription.png' | relative_url }}" width="550" text-align=center alt="img1" />
</center>

<br>

<!-- equipe -->
<center><h3 class="post-title">Equipe de desenvolvimento</h3><br/></center>
<div class="row">
  <div class=" col-xl-auto offset-xl-0 col-lg-4 offset-lg-0">
    <table class="table-borderless highlight">
      <thead>
        <tr>
          <th><center><a href="https://www.linkedin.com/in/mateus-seixas-59296a190/" target="_blank">
                <p align="center">
                    <img src="{{ 'assets/img/people/mateusseixas-1.png' | relative_url }}" alt="Not found" width="100" class="img-fluid rounded-circle" />
                </p>
            </a></center></th>
            <th></th>
             <th><center><a href="https://www.linkedin.com/in/diogo-alexandre-martins/" target="_blank">
                <p align="center">
                    <img src="{{ 'assets/img/people/diogomartins-1.png' | relative_url }}" alt="Not found" width="100" class="img-fluid rounded-circle" />
                </p>
            </a></center></th>
          <th></th>
          <th><center><a href="https://mhar-vell.github.io/portfolio/" target="_blank">
                <p align="center">
                    <img src="{{ 'assets/img/people/marcoreis8b&w-1.png' | relative_url }}" alt="marco" width="100" class="img-fluid rounded-circle" />
                </p>
            </a></center></th>
            <th></th>
          <th><center><a href="https://mhar-vell.github.io/portfolio/" target="_blank">
                <p align="center">
                    <img src="{{ 'assets/img/people/marcoreis8b&w-1.png' | relative_url }}" alt="marco" width="100" class="img-fluid rounded-circle" />
                </p>
            </a></center></th>
        </tr>
      </thead>
      <tbody>
        <tr class="font-weight-bolder" style="text-align: center margin-top: 0">
          <td width="25%">Mateus Seixas</td>
          <td></td>
          <td width="25%">Erick Suzart</td>
          <td></td>
          <td width="25%">Tiago Barreto</td>
          <td></td>
          <td width="25%">Marco Reis</td>
        </tr>
        <tr style="text-align: center" >
          <td style="vertical-align: top;text-align: justify;"><small>Pesquisador em Robótica no Centro de Competências em Robótica e Sistemas Autônomos do Senai Cimatec. Graduado e mestrando em Engenharia Elétrica pela Universidade Federal da Bahia. Amante da natureza.</small></td>
          <td></td>
          <td style="vertical-align: top;text-align: justify;"><small>Ajuda.</small></td>
          <td></td>
          <td style="vertical-align: top;text-align: justify;"><small>Ajuda.</small></td>
          <td></td>
          <td style="vertical-align: top;text-align: justify;"><small>Pesquisador Sênior do projeto <br>Mestre em Engenharia de Produção e Eng. Eletricista.</small></td>
        </tr>
      </tbody>
    </table>
  </div>
</div>

<br>

### Resumo do Projeto
1. Categoria: <font color="#fbb117">Aerial Robotics</font>
2. Prazo: <font color="#fbb117">8 meses</font>
3. Data de início: <font color="#fbb117">01/maio/2022</font>
4. Data de término: <font color="#fbb117">22/dezembro/2022</font>
<!-- 5. Repositório robô real: <a href="https://github.com/Brazilian-Institute-of-Robotics/bir_bbot"><font>Carcara</font></a> -->
<!-- 5. Repositório robô simulado: <a href="https://github.com/Brazilian-Institute-of-Robotics/bir_bbot-simulation"><font>Bir_Bbot-simulation</font></a> -->
5. Sponsor: <a href="http://www.senaicimatec.com.br/en/"><font color="#fbb117">Senai CIMATEC</font></a>
<!-- 6. Recursos materiais: <font color="#fbb117">$USD 3162,64</font> -->
<!-- 8. Apresentação URL: <a href="https://github.com/Brazilian-Institute-of-Robotics/bir_bbot-docs"><font>Bbot-docs</font></a> -->
<!-- 9. Report URL: <a href="https://github.com/Brazilian-Institute-of-Robotics/bir_bbot-docs/tree/doc/report"><font>Bbot-report</font></a> -->
<!-- 10. Artigos produzidos:  -->

<br>

### Referências

<!-- 1. <a id="GURTNER">**Adam Kollarčík and Martin Gurtner**</a>; Modeling and Control of Two-Legged Wheeled Robot; Master’s thesis, CZECH TECHNICAL UNIVERSITY IN PRAGUE. 2021. -->
<!-- 1. <a id="SANTOS">**Santos, Gabriel da Silva; Cardoso, Etevaldo; Reis, Marco Antonio dos**</a>; "Localização de Robôs Móveis em Ambiente Internos usando Marcos Fiduciais", p. 226-233 . In: **Anais do V Simpósio Internacional de Inovação e Tecnologia**. São Paulo: Blucher, 2019. -->

<br>
<hr class="mark">
<div id="full-tags-list">
<h3 class="post-title"><font color="#fbb117">Posts</font></h3>
  {%- for tag in tags_list -%}
      <h4 id="{{- tag -}}" class="linked-section">
          <i class="fas fa-tag" aria-hidden="true"></i>
          &nbsp;{{- tag -}}&nbsp;({{site.tags[tag].size}})
      </h4>
      <div class="post-list">
          {%- for post in site.tags[tag] -%}
              <div class="tag-entry">
                  <a href="{{ post.url | relative_url }}">{{- post.title -}}</a>
                  <div class="entry-date">
                      <time datetime="{{- post.date | date_to_xmlschema -}}">{{- post.date | date: date_format -}}</time>
                  </div>
              </div>
          {%- endfor -%}
      </div>
  {%- endfor -%}
</div>
