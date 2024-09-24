{
  "name": "realtrac-crm",
  "version": "3.0.1",
  "description": "RealTrac",
  "author": "RealTrac",
  "homepage": "http://localhost:3000/",
  "dependencies": {
    "@ant-design/icons": "^5.3.6",
    "@date-io/date-fns": "1.3.13",
    "@emotion/react": "^11.4.1",
    "@emotion/styled": "^11.3.0",
    "@material-ui/core": "^4.12.3",
    "@material-ui/icons": "^4.9.1",
    "@material-ui/lab": "^4.0.0-alpha.49",
    "@material-ui/pickers": "^3.2.10",
    "@mui/icons-material": "^5.0.5",
    "@mui/lab": "^5.0.0-alpha.48",
    "@mui/material": "^5.0.1",
    "antd": "^5.16.5",
    "axios": "^0.19.2",
    "comma-number": "^2.0.1",
    "date-fns": "^2.14.0",
    "dayjs": "^1.11.10",
    "inter-font": "^3.19.0",
    "lodash": "^4.17.20",
    "moment": "2.18.1",
    "mui-datatables": "^2.14.0",
    "papaparse": "^5.4.1",
    "react": "^16.13.1",
    "react-barcode": "^1.4.0",
    "react-barcodes": "^1.1.0",
    "react-dom": "^16.13.1",
    "react-file-reader": "^1.1.4",
    "react-font": "^1.2.1",
    "react-html-parser": "^2.0.2",
    "react-redux": "^7.2.0",
    "react-responsive-modal": "^6.0.0",
    "react-router-dom": "^5.1.2",
    "react-row-select-table": "^1.0.16",
    "react-scripts": "3.4.1",
    "react-select": "^4.3.1",
    "react-to-print": "2.0.0-alpha-1",
    "recharts": "^2.12.0",
    "redux": "^4.0.5",
    "redux-persist": "^6.0.0",
    "semantic-ui-react": "^2.0.3",
    "serve": "^14.2.1",
    "socket.io-client": "^2.3.0",
    "sweetalert": "^2.1.2",
    "typescript": "^4.1.3",
    "xlsx": "0.18.5"
  },
  "scripts": {
    "start": "set PORT=8080 && react-scripts start",
    "react-build": "react-scripts  build",
    "build": "yarn react-build",
    "test": "react-scripts test",
    "prod": "npm run build && serve build"
  },
  "eslintConfig": {
    "extends": "react-app"
  },
  "browserslist": {
    "production": [
      ">0.2%",
      "not dead",
      "not op_mini all"
    ],
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ]
  }
}
