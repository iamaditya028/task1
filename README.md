# task1
Flow Chart using Graphviz
 digraph G 
{	node [fontname = "handlee"];

	edge [fontname = "handlee"];


	start [

	label = "Start";
	shape = oval;
	];

	url [
	label= "Enter Uniform Resource locator";
	shape= parallelogram;
	];

	check [
	label= "check cache";
	shape= diamond;
	];

	bcache [
	label= "DNS search for cache in browser";
	shape= diamond;
	];

	ocache [
	label= "DNS lookup for operating system cache";
	shape= diamond;
	];

	icache [
	label= "DNS lookup for ISP(Internet Service Provider)";
	shape= diamond;
	];

	sh [
	label= "Shows the Image of the website if previsited";
	shape= rectangle;
	];

	d[
	label= "ISP initiates DNS query and provide IP address";
	shape= rectangle;
	];


	t [
	label= "TCP Connection between two servers (3 way handshake technique)";
	shape= rectangle;
	];

	b [
	label= "Browser sends http request to the web server";
	shape= rectangle;
	];

	s [
	label= "Server sends back http response";
	shape= rectangle;
	];

	h[
	label= "Browser displays HTML content";
	shape= rectangle;
	];
	st[
	label= "Stop";
	shape= oval;
	];


	start -> url;
	url-> check [ label = "yes" ];
	check-> bcache [ label = "True"];
	bcache -> ocache [ label = "False"];
	ocache -> icache [ label = "False"];
	icache:s -> d:s [label = “True”];
	check -> d [ label = "False"];
	d -> t;
	t -> b -> s -> h -> st;

}
