---
title: Demonstração das funcionalidades
logo:
    src: https://blog-do-lucao.vercel.app/apple-touch-icon.png
    alt: Lucão
reveal:
    a: 2
---

# Demonstração dos testes usando Reveal e Hugo

---

## Funciona a logo da Internet
- A logo é importada como asset então é redistribuida com o site gerado
- Tem que ser num formato mais padrão tipo PNG ou JPG senão o hugo reclama que não sabe lidar

----
%auto-animate%

## Funciona código

```java
public class Main {
    public static void main(String args[]) {
        System.out.println("aha");
    }
}
// Parece bem funcional pra mim
```

---
%auto-animate%

## Funciona código

```nix
# Svelte reclamava bastante desse trecho
{ pkgs ? import <nixpkgs> {} }:

pkgs.mkShell {
    buildInputs = with pkgs; [ hugo ];
}
# Fun fact: o próprio Hugo faz o syntax highlight
```

---

## Funciona matemática

- $$x^2$$
- $$\frac{-b \pm \sqrt{b^2 -4ac}}{2a}$$

---

## Funciona mermaid

{{<mermaid align="left">}}
sequenceDiagram
    participant Alice
    participant Bob
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Rational thoughts <br/>prevail!
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
{{</mermaid>}}

---

## Funciona HTML arbitrário
- Precisa ativar uma flag na configuração do hugo pra dar certo

<button onclick="alert('vai dizer que não')">Testar</button>

---
## Funciona embed

<iframe width="420" height="315" allowfullscreen src="https://www.youtube.com/embed/dQw4w9WgXcQ?autoplay=0&mute=0">
</iframe>

---
%auto-animate%
## Animações

<p>AAAA</p>

---
%auto-animate%
## Animações

<p color="red">AAAA</p>

---
<style>
img.block {
width: 100px; height: 100px;
margin: auto;
}
</style>

%auto-animate%

## Animações

<img class="block" style="background-color: red"></img>

---
%auto-animate%

## Animações

<img class="block" style="background-color: blue; margin-top: 100px"></img>

---

## E GIFs

<img src="{{< vendor "https://steamuserimages-a.akamaihd.net/ugc/2480808807594637252/11119ACEA65BD9BE6A94AC9DEA436C0805BC2566/?imw=5000&imh=5000&ima=fit&impolicy=Letterbox&imcolor=%23000000&letterbox=false" >}}" />

---

## E templates?

{{% eval.inline %}}
isso foi gerado em tempo de build: {{ now.Format "2006.01.02" }}
{{< /eval.inline >}}

{{% identity.inline %}}
isso foi gerado em tempo de build: {{ now.Format "2006.01.02" }}
{{% /identity.inline %}}
