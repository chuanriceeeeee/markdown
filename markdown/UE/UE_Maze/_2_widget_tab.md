<style>
h1,h2,h3,h4,h5{font-size:22px !important;}
</style>

# words


# 1. use interface
- widget blueprints
  >interface button
# 2. widget blueprints
- vertical box
- horizental box
## 2.1 inherit
- change inherit can change change the relationship in different buttons
## 2.2 WidgetSwitcher
- offer switch button

# 3. button blueprint
```mermaid
graph TD

A(Onclick)-->B{if Active Widget Index==Onclick Button Index}
B---->C[Set Active Widget Index=0]
B--else-->D[Set Active Widget Index=Onclick Button Index]
C-->E[Set Button Color]
D-->E
E-->F[Make Button Array]
F-->G[For Each loop]-->H{Is Valid}-->I{Button Array Index==Active Widget Index}-->J[Set Active Button Color]
I--else-->K[Set Inactive Button Color]

subgraph Set Widget Index
B
C
D
end
subgraph Set Button Color
E
F
G
H
I
J
K
end


```
## 3.1 Onclick
- examine button click
## 3.2 Get Active Widget Click
