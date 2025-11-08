Problem: How can i trace my trail on the decisions i made when writing a piece of software so that there is a recorded history of how a piece of software evolved and what the reasoning behind it was

>>> This is quite important because you may have to take a break from the work for a while and revisit some time later where your mind is not aware of the contexts anymore. Likewise someone else may come into the project fresh with 0 context. Having no way of justifying why software is designed in certain ways and why certain contradictions or anomalies occur throughout the codebase can really slow down the development and hamper the quality without a name.

One way I solve this is by writing rich git commit messages. Commit messages are **already** a audit trail of the decisions you make but developers do tend to be lazy with writing them. They write vague messages that are self explanatory rather than mentioning the reasons behind certain changes and what their effects are.

by using a framework like:

What changed?
Why did it change?
What was the effect

each commit now has a rich context and you now have a bank of rich data which you can perform further data analysis and uncover insights from

