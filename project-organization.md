# Project Organization

In general, all projects will be organized in a folders-by-feature structure as opposed to the somewhat more traditional folders-by-type structure. This means that a given feature’s routes, controllers, models, services, etc. will all be organized within a single folder for the feature.

A good way to remember this is to follow the LIFT principle, which dictates that we be able to:
1. Locate our code easily
1. Identify code at a glance
1. Maintain a Flat structure as long as we can
1. Try to stay DRY (Don’t Repeat Yourself)

This principle encourages us to keep things simple and reduce over-optimization and early complexity.

Folder and file names should use the “dash” style for replacing spaces. For example, a feature known as “Sales Orders” would be in a `sales-order` folder, the Sales Order controller would be in a file named `sales-order.controller.go`.
