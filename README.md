# ALU_maths

`timescale 1ns / 1ps


module Alu(f,a,b,op);
input [7:0]a,b;
output reg[7:0]f;
input [1:0]op;
parameter ADD = 2'b00;
parameter SUB = 2'b01;
parameter MUL = 2'b10;
parameter DIV = 2'b11;
always @(*)
begin
case(op)
ADD:f=a+b;
SUB:f=a-b;
MUL:f=a*b;
DIV:f=a/b;
endcase
end

endmodule




with if-else :-


`timescale 1ns / 1ps

module Alu(f, a, b, op);
    input [7:0] a, b;
    output reg [7:0] f;
    input [1:0] op;

    parameter ADD = 2'b00;
    parameter SUB = 2'b01;
    parameter MUL = 2'b10;
    parameter DIV = 2'b11;

    always @(*) begin
        if (op == ADD)
            f = a + b;
        else if (op == SUB)
            f = a - b;
        else if (op == MUL)
            f = a * b;
        else if (op == DIV)
            f = (b != 0) ? a / b : 8'b0; // Prevent division by zero
        else
            f = 8'b0; // Default case to handle unexpected values of op
    end
endmodule

