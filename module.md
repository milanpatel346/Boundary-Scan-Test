# Boundary-Scan-Test

module main(
						input Data_in,Scan_in,
						input ShiftSR,UpdateSR,ClockSR,clk,mode,
						output reg Data_out,Scan_out,
						output reg q1,q2,k
						);
always@(posedge clk)
begin
if(mode)
begin
if(ShiftSR)
begin
k=Data_in;
end
else
begin
k=Scan_in;
end
if(ClockSR)
begin
q1=k;
end
else
begin
end
if(UpdateSR)
begin
q2=q1;
end
else
begin
Scan_out=q1;
end
Data_out=q2;
end
else
begin
Data_out=Data_in;
end
end
endmodule
