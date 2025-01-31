---
sidebar_position: 4
title: Slim CI
description: Running only the diffs you need
---

By default, Datafold will run Data Diffs on any models that are edited in the Pull Request as well as any downstream models.

In some cases, this leads to too much diffing, which can be overwhelming and slow. That's why we've created the Slim CI configuration, which only diffs modified models. You still have the option of diffing individual downstream models, or automatically diffing all downstreams.

<iframe width="640" height="414" src="https://www.loom.com/embed/ab29774ab6314df6bcc4dd70a5e75aa9" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

### How it works

To enable Slim CI by default on all future commits that are pushed to GitHub or GitLab, select the Slim CI checkbox in your orchestration settings.

<img width="461" alt="Screen Shot 2022-11-21 at 1 18 00 PM" src="https://user-images.githubusercontent.com/1799931/203393699-7f46dc94-203f-427b-b39d-a0806d11e5e8.png"></img>

When you push a change, you'll see that Data Diffs have been run for only the modified models.

<img width="1008" alt="Screen Shot 2022-11-22 at 10 32 57 AM" src="https://user-images.githubusercontent.com/1799931/203394628-3000ca4d-fd00-40c6-a865-1161a60d014f.png"></img>

This Pull Request has one modified data model, for which a Data Diff was run. That model has two downstream dependent models, which were identified, but Data Diffs were not run.

You also have the option within the PR to click and run any downstream Data Diffs.

<img width="857" alt="Screen Shot 2022-11-22 at 10 33 31 AM" src="https://user-images.githubusercontent.com/1799931/203393999-0499c241-c74d-4715-b30b-7652877a2aa0.png"></img>

Finally, you can apply the datafold:full label to the PR, which will automatically run all downstream Data Diffs.

<img width="984" alt="Screen Shot 2022-11-22 at 10 34 12 AM" src="https://user-images.githubusercontent.com/1799931/203394318-414e5f48-7310-4926-baa8-84b76ddebbf6.png"></img>


