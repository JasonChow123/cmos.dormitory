# cmos.dormitory

Dormitory Points & Rewards System — a lightweight platform designed for managing points, evaluations, and redemptions in dormitory or shared-living scenarios.

## Project Overview
cmos.dormitory turns daily dorm activities (cleaning, duty shifts, participation, infractions, etc.) into quantifiable "points" and provides a transparent, auditable process for issuing and redeeming those points. The system supports multiple roles (admin, dorm leader, member) with clear permission boundaries to make dorm self-governance and management committee operations straightforward.

## Core Features
- Points management: automatic or manual awarding and deduction of points via rules for tasks, inspections, activity check-ins, and infractions.
- Redemption: members can redeem points for goods, vouchers or services (e.g., laundry pass, equipment borrowing).
- Approval and audit: configurable approval workflows for redemptions and a complete transaction log for every points change.
- Multi-role support: Admin (configure rules, manage products, approve), Dorm Leader (submit assessments, approve small redemptions), Member (view points, request redemptions).
- Notifications: notify users of points changes and redemption status via in-app notifications, email, or SMS (optional).
- Extensible catalog and rules engine to support promotions and bulk issuances.

## Use Cases
- Campus dormitory incentive programs (cleanliness, duty roster, civilized dorm awards)
- Staff dormitories or co-living spaces that want a lightweight rewards system
- Event reward systems with physical / service exchange

## Technical Highlights (example)
- Clear frontend / backend separation for easier development and deployment
- Configurable scoring rules to reduce the need for code changes for common ops
- Audit logging and transactional safety to ensure correctness of points flows

## Quick Start — Based on this repository's current contents

> Note: the repository currently contains a static `index.html`. The instructions below cover how to preview that static site, and also include guidance for when a backend or Node.js app is added later.

1. Clone the repository
```bash
git clone https://github.com/JasonChow123/cmos.dormitory.git
cd cmos.dormitory
```

2. Inspect repository to determine project type
```bash
ls -la
# Check for Node.js project files
if [ -f package.json ]; then
  echo "Found package.json"
else
  echo "No package.json found — repository appears to be a static site"
fi
```

3. Serving the static site (current state: index.html present)
- Open directly:
  - Double-click `index.html` or open it in your browser (`file://...`).
- Serve locally (recommended to avoid file:// restrictions):

Python 3:
```bash
python3 -m http.server 8000
# open http://localhost:8000
```

Node (npx serve):
```bash
npx serve . -l 3000
# open http://localhost:3000
```

VS Code:
- Use the Live Server extension and click "Go Live" on `index.html`.

4. If/when this repo contains a Node.js app (i.e., `package.json` is added)
```bash
# install dependencies
npm install

# start in development (script names may vary)
npm run dev
# or
npm start
```

If the project later separates into `backend/` and `frontend/` directories:
```bash
# backend
cd backend
npm install
npm run dev

# frontend
cd ../frontend
npm install
npm run dev
```

5. Environment & database (only relevant when a backend exists)
- Copy `.env.sample` and fill real values:
```bash
cp .env.sample .env
# edit .env with your secrets and DB connection
```

- Example migration commands (replace with your project's tool):
Prisma:
```bash
npx prisma migrate dev --name init
```
TypeORM:
```bash
npm run typeorm migration:run
```
Sequelize:
```bash
npx sequelize-cli db:migrate
```

6. Troubleshooting tips
- If static assets (JS/CSS/images) are missing, check their relative paths from `index.html`.
- For JS errors, open DevTools Console to inspect stack traces.
- If you expect a backend but only see `index.html`, check other branches, submodules, or ask the maintainer for the server repo.

## Contribution
See CONTRIBUTING.md for contribution guidelines.

## Contact & Support
Maintainer: @JasonChow123

## License
Add project license here (e.g., MIT, Apache-2.0).