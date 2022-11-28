# Descri-o-Comportamental

<br>

##Exercício 1:
=
<br>

module exercicio ( j, k, clk, q );
<br>
  input clk, j, k, rst;
  <br>
  output reg q;
  <br>
  always @(negedge clk, negedge rst) begin
  <br>

    if (~rst) begin
    <br>
     q <= 1'b0;
     <br>
    end
    <br>
    else if(k == 1 & j == 0) begin 
    <br>
     q <= 1'b0;
     <br>
    end
    <br>
    else if(k == 0 & j == 1) begin
    <br>
     q <= 1'b1;
     <br>
    end
    <br>
    else if(k == 1 & j == 1) begin
    <br>
     q <= ~q;
     <br>
    end
    <br>
    
  end
  <br>
endmodule

##Exercício 2:
=
<br>

module exercicio (s, r, clk, q);
<br>
input clk, s, r;
<br>
output reg q;
<br>
always @(negedge clk) begin
<br>
if (s == 0 & r == 0) begin
     q <= q;
    end
    else if(s == 1 & r == 0) begin 
     q <= 1'b1;
    end
    else if(s == 0 & r == 1) begin
     q <= 1'b0;
    end
    else if(s == 1 & r == 1) begin
     q = 1'b1;
    end
    
  end
  
endmodule


##Exercício 2:
=

<br>
module exercicio(a, enable, q);
<br>
input a;
<br>
input enable;
<br>
output reg q;
<br>
always @(a or enable) begin
<br>

if(enable)
    case (a)
      1'b0 : q <= 1'b0;
      1'b1 : q <= 1'b1;
      default : q <= 1'b0;
    endcase
    else q <= 1'bz;

  end
endmodule

##Exercício 3:
=
<br>
module exercicio(a, enable, q);
  // Declaração de portas
  input a;
  input enable;
  output reg q;

  // Descrição comportamental
  always @(a or enable) begin
    if(enable)
    casex (a)
      1'b0 : q <= 1'b0;
      1'b1 : q <= 1'b1;
      default : q <= 1'b0;
    endcase
    else q <= 1'bz;

  end
endmodule

##Exercício 4:
=
<br>

module exercicio (a,b,d,borrow);

  // Declaração de portas
  input [3:0] a, b;
  output reg borrow;
  output reg [3:0] d;

  // Variáveis auxiliares
  reg c;
  integer i;

  // Descrição comportamental
  always @(*) begin
    for (i = 0; i <= 3; i=i+1) begin
      d[i] = a[i] - b[i];
      c = (a[i] & b[i]);
    end
    borrow = c;
  end

endmodule

##Exercício 5:
=
<br>
