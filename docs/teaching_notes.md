---
layout: default
title: "Teaching notes"
nav_exclude: true
has_toc: true
search_exclude: true
---

# Teaching notes

{: .info }
Based on the [pedagogical concept](pedagogy.html). Administrative tasks are [here](https://digital-work-lab.github.io/handbook/docs/30-teaching/32_courses/){: target="_blank"}.

| **Week** | **Duration** | **Topic**        | **Preparation**                      | **Session Notes**                                          |
|----------|--------------|------------------|--------------------------------------|------------------------------------------------------------|
| 1        | 90 min       | Topics           | [Preparation](#topics)               | [Session notes](week_1_teaching_notes.html)                |
| 2        | 180 min      | Git              | [Preparation](#git)                  | [Session notes](week_2_git_teaching_notes.html)            |
| 3        | 180 min      | Python 1         | [Preparation](#python)               | [Session notes](week_3_python_teaching_notes_1.html)       |
| 3        | 180 min      | Python 2         | [Preparation](#python)               | [Session notes](week_3_python_teaching_notes_2.html)       |
| 4        | -            | Group-work       | -                                    |                                                            |
| 5        | 90 min       | Best Practices   | [Preparation](#best-practices)       | [Session notes](week_5_best_practices_teaching_notes.html) |
| 6-11     | -            | Group-work       | -                                    |                                                            |
| 12       | Flexible     | Code Review      | [Preparation](#code-review)          | [Session notes](week_12_code_review_teaching_notes.html)   |

## Preparation

- [ ] Announce project on [instagram](https://www.instagram.com/informatik_unibamberg/){: target="_blank"}
- [ ] Advertise the project in the lecture or other courses based on the [mailing](mailings.html#advertising) - check if not applicable
- [ ] Update dates and rooms for sessions
- [ ] Update the rating average in the badge (change the badge-link on index.md) and participation
- [ ] Review the [pedagogical concept](pedagogy.html) in preparation of the project
- [ ] Check whether `pre-commit run --all` runs without errors in Codespaces
- [ ] Check whether `colrev package --init` works

<details markdown="block">
<summary>Student communication notes</summary>

> The overlap is a bit unfortunate and it is difficult for me to understand whether you will be able to contribute to the project work if you miss these sessions. At the same time, I would like you to participate in the project, and prior experience with Python and Git certainly helps.
> 
> What I would suggest going forward is to check the materials of the sessions (available at https://digital-work-lab.github.io/open-source-project/), and to start finding a team (as described in the slides for the first session). Naturally, we expect everyone, including yourself, to contribute equally to the project.
> 
> If you have any questions on the process or materials, please let me know - I am happy to help.

</details>

<br>

{: .info }
> All of the following items must be completed **before the session** unless stated otherwise.

## Week 1: Topics <a id="topics"></a>

- [ ] Send out [welcome and information mailing](mailings.html#welcome) before the first session
- [ ] Link the [feedback issue](https://github.com/digital-work-lab/open-source-project/issues){: target="_blank"} in VC, explain our process of evaluation and improvement, summarize our improvements from last semester

## Week 2: Git  <a id="git"></a>

- [ ] Check whether the `rec_dict.patch` applies (`git diff > rec_dict.patch`)
- [ ] Print some of the [overviews](https://github.com/digital-work-lab/practice-git/blob/main/notebooks/img/overview-task.pdf){: target="_blank"}
- [ ] Send out [comment-on-issues mailing](mailings.html#comment-issues)

## Week 3: Python <a id="python"></a>

- [ ] Prepare the `tutorial_python` branch and update the commit-SHAs in the notebooks

<details markdown="block">
<summary>Python prep</summary>

```
git checkout tutorial_python
git branch tutorial_backup
git rebase -i HEAD~16
# edit the "update click" commit (before the tutorial starts) with the latest pyproject.toml / poetry update to update poetry.lock
git rebase main
git push -f
```

When the poetry.lock/pyproject.toml fail: checkout --ours poetry.lock/pyproject.toml, poetry add bibtexparser
</details>

- [ ] Create a list of topics and students (first/second choice) and facilitate issue discussions

<details markdown="block">
<summary>Facilitating issue discussions</summary>

> Thank you, @pmao0907 and @MingxinJiang for offering to switch to #360 . This leaves a group of 3 with @CelinaSchwarz , @omanovb and @QuynhMaiNguyen 👍 Can you select a group lead, fork the repository and link your repository in this feed?

</details>

## Week 4: Group work (no session)

- [ ] Distribute the [survey](../assets/Interim_Project_Assessment_Survey.docx) via VC, asking students to upload it (upload box).
- [ ] Send out the [prep-best-practices mailing](mailings.html#prep-best-practice)
- [ ] In the issue feeds, ask students to link their fork

## Week 5: Best practices <a id="best-practices"></a>

- [ ] Review responses from the survey and prepare the session

## Weeks 6-11: Group work / Hacking sessions

Guidelines for the hacking sessions:

- Ask questions instead of offering solutions
- Suggest the use of Iterators for API retrieval

## Week 7

- [ ] Send out [hacking-sessions mailing](mailings.html#hacking-sessions)

## Week 10

- [ ] Send out [pull-request mailing](mailings.html#pull-request)
- [ ] Send out [evaluation mailing](mailings.html#evaluation)

## Week 12: Code review <a id="code-review"></a>

{: .highlight }
> The code review session should be in my office (with a Computer screen connected via a long HDMI cable).

- [ ] Print and pre-fill [evaluation sheets](https://github.com/digital-work-lab/open-source-project/tree/main/assets/evaluation){: target="_blank"}
- [ ] Check whether connectors (e.g., HDMI) are required and provide them
- [ ] If projects require access tokens (API keys), provide them to the group
- [ ] Remind students to complete the evaluation

After the session:

- [ ] For implementing the feedback from the pull request, we should ensure that efforts are fair between teams (e.g., selecting issues to address or adding suggestions)
- [ ] Include a summary of todos in the pull request

```
Hello @x, @y,

following up on the code review session, I took the following notes. Please address them by **XXXXXX**:

- [ ] Fix the pre-commit warnings (the line-too-long warnings can be ignored in the test files)
- [ ] Reduce information printed when running  `colrev search` (ideally, one line per record)
- [ ] Add the volume/number fields (if possible)
- [ ] Remove unnecessary files/changes from pull request (e.g., `.pre-commit-conig.yaml`, `colrev/ops/search.py`, or the `search` submodule)

If there is anything I can help with, please let me know 👏
```

After feedback was implemented by the students

- [ ] Send out [project completion mailing](mailings.html#completion-post)
- [ ] Notify students about the option to observe the merge and release process (Zoom meeting)
- [ ] Merge pull requests and add contributors (see [merge-notes](merge_notes.html))
