# Web-Analyzer-Project-3
All three projects are themed around the topic of web server analysis. They are designed to culminate in a limited simulation and assessment of a web server if all project tasks are properly completed. In Project 1, we computed some statistics on the resources that are served. In Project 2, we incorporated client-requests to an extent. In this Project, we incorporate client-requests with priorities, and a light version of Discrete Event Simulations.

In ece150-proj3-provided.h, following is the data-type that pertains to the server's database.

struct uri {
  char *name;
  unsigned size, priority;
  uri *next;
};

As the above datatype suggests, the server's database is a linked list of entries: a URI name, size and priority. The following types are used to represent client-requests. That is, client-requests are provided as a linked list as well, each entry of type request. The timestamp is the time at which the client-request arrives.

How the server works: A client-request arrives, and is instantaneously queued. Once queued, the client-request is ready to be processed by the server. Client-requests that are pending are processed based on the priority of the URI being requested. A higher number means a higher priority. 

What you need to do: Implement the following function.

timestamp maxClientDelay(uri *, request *);

The first argument is a linked list that is the database at the server. The second is a linked list of client-requests, sorted by non-decreasing timestamp. The function returns the maximum delay, rounded to the nearest second, incurred by a client-request from the time it arrives till the time it is chosen to by processed by the server.

Implement a Discrete Event Simulation of the server to compute the result the above function returns. One of three events can happen at the server at any given moment in the simulation. (a) Time progresses. (b) Requests are queued. (c) A pending request is serviced.
