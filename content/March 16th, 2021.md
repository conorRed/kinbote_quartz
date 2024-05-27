- Jira for error page on UI?
- Am I on pager duty?
- https://www.youtube.com/watch?v=3-KwVlgAOZ4 pretty excellent video on difficulty in reading. Or 'tackling' and 'conquering' books. Sometimes you aren't ready, why not just read things that interest you or challenge you not because other people tell you what you should think of it. I think its kinda cool to read a book that is beyond your years almost, that you might have to skip or come back to when you've done a bit of living, or are more mature. Maybe not all books are on equal footing. They can't all be interpreted at any time in your life.
    - Artwork as a representation of someones reality
- Being consistently late to meetings!
- Last year, around the world, nearly [two billion tons](https://www.worldsteel.org/steel-by-topic/statistics/steel-data-viewer/MCSP_crude_steel_monthly/WORLD_ALL) of steel was produced — more than 500 pounds for every person on earth. And at least [30 billion tons](https://www.usgs.gov/centers/nmic/cement-statistics-and-information) of concrete, or nearly 9,000 pounds for each of us.
- One interesting thing I thought about this morning with climate change, that in order for sustainability to become a part of society it necessarily requires thought of the group as opposed to the individual, it could be another reason a lot of people fear the future restraints for the good of the community as opposed to the consumer, or the individual.
- [talks about deflationary cycles effect on the Bitcoin price, didnt really understand it](https://medium.com/concoda/this-is-what-it-will-take-for-bitcoin-to-reach-100-000-c5082281b17e)
    - Probably need to do more research on economic cycles, deflation, stagflation etc.
- [Nice article on history of mars rovers](https://medium.com/starts-with-a-bang/witness-mars-from-the-perspective-of-every-successful-lander-and-rover-b7cd51ff5c4d)
- #Book Harold Bloom's critical views
- [Borg, Omega and Kubernetes](https://queue.acm.org/detail.cfm?id=2898444#content-comments)
    - First container management system at Google was called Borg. Built to manage long-running services and batch jobs. Google contributed much of the container code to the Linux kernel
    - An ecosystem started to develop around Borg based on the needs of different teams inside of Google. Remains the primary container-management system with Google.
    - Omega was driven by a desire to improve the software engineering of Borg ecosystem. Stored the state of the cluster in a transaction oriented store. Decoupling allowed for separation of Borg functionality [[?]]
    - Then came [[Kubernetes]] whcih used the same type of persistent store as Omega but used a domain-specific REST API to dish out control of the control plane. This allowed for a more diversified array of clients
    - Google utilised and co developed container technology for to interlock batch jobs with user facing jobs. "he isolation is not perfect, though: containers cannot prevent interference in resources that the operating-system kernel doesn't manage, such as level 3 processor caches and memory bandwidth, and containers need to be supported by an additional security layer (such as virtual machines) to protect against the kinds of malicious actors found in the cloud."
    - Containers nowadays are really an image (collection of files , package) and an isolation mechanism (e.g. docker daemon)
    - "Containerization transforms the data center from being machine oriented to being application oriented."
    - "__Containers encapsulate the application environment__"
        - "The original purpose of the cgroup, chroot, and namespace facilities in the kernel was to protect applications from noisy, nosey, and messy neighbors. Combining these with container images created an abstraction that also isolates applications from the (heterogeneous) operating systems on which they run. This decoupling of image and OS makes it possible to provide the same deployment environment in both development and production, which, in turn, improves deployment reliability and speeds up development by reducing inconsistencies and friction."
        - The key is to encapsulate the applications dependency into a package that can be deployed into the container. __hermetic images__
    - "__Managing containers means managing applications rather than machines__"
        - Management API's can be geared towards the container (application) as opposed to the underlying hardware
        - Metrics for the underlying hardware can also be taken using resource segregation info from cgroup
        - Divide between application and machine monitoring
        - "The application-oriented shift has ripple effects throughout the management infrastructure. Our load balancers don't balance traffic across machines; they balance across application instances. Logs are keyed by application, not machine, so they can easily be collected and aggregated across instances without pollution from multiple applications or system operations."
            - "although so far we have focused on applications being 1:1 with containers, in reality we use nested containers that are co-scheduled on the same machine: the outermost one provides a pool of resources; the inner ones provide deployment isolation." Pod in Kubernetes. Common patterns is other supporting containers to provide logging or other resources to the main application container in the pod.
        - Borg ecosystem added complexity through different tooling having different conventions. Kubernetes attempts to have a consistent approach to APIs. e.g. the object metadata, spec and status fields as standard.
    - "The design of Kubernetes as a combination of microservices and small control loops is an example of control through __choreography__—achieving a desired emergent behavior by combining the effects of separate, autonomous entities that collaborate. This is a conscious design choice in contrast to a centralized __orchestration system__, which may be easier to construct at first but tends to become brittle and rigid over time, especially in the presence of unanticipated errors or state changes."
    - 