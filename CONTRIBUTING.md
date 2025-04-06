# :handshake: Contribution Guidelines

## :gift: Contribution Types
We accept three types of contributions with quality requirements:

### :scroll: Paper Additions (CVPR/ICCV/ECCV/JSTARS/TGRS/etc)
- :newspaper: **Conference Papers** (Last 2 years)
- :blue_book: **Journal Articles** (JCR Q1/Q2)
- :notebook_with_decorative_cover: **Technical Reports** (With peer-review)

### :computer: Code Implementations
- :pytorch: **PyTorch Frameworks** (1.8+)
- :robot: **Pretrained Models** (Provide weights link)
- :bar_chart: **Reproducibility** (Include benchmark results)

### :floppy_disk: Dataset Contributions
- :satellite: **RS Specific**
- :label: **Annotation Quality**
- :balance_scale: **License Clearance**

## :rocket: Submission Process
1. Fork the repository
2. Create feature branch:
   ```bash
   git checkout -b feat/add-[resource-name]
   ```
3. Add resource to appropriate section
4. Submit PR with template:

```markdown
## :mag_right: Resource Type
- [ ] Paper
- [ ] Code 
- [ ] Dataset

## :pencil2: Description
50-100 words highlighting technical novelty

## :white_check_mark: Verification
- [ ] Code runs with original paper claims (For code)
- [ ] Dataset license verified (For data)
- [ ] Added unit tests (For code)
```

## :triangular_ruler: Code Standards
- :snake: Python 3.8+ with type annotations
- :test_tube: Unit Test Coverage ≥ 90%
- :books: Docstring following Google Style
- :docker: Docker Support (Optional but recommended)
## :hourglass_flowing_sand: Review Process
- :alarm_clock: 24h Response for initial review
- :label: Update Tags :
  - needs-update : Requires modifications
  - awaiting-author : Waiting for contributor response
  - approved : Ready for merging
- :email: Notification via GitHub mentions
:construction: For large contributions (>500 LOC), please open an issue first for design discussion.