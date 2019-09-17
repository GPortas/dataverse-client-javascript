# dataverse-client-javascript
A JavaScript/TypeScript client for [Dataverse](http://guides.dataverse.org/en/latest/api/).

## NPM
Module available as `js-dataverse` at https://www.npmjs.com/package/js-dataverse

## Usage
Create a new client:
```
const client = new DataverseClient('https://demo.dataverse.org/')
```

Request dataset information:
```
const response = await client.getDataverseInformation('myDataverseAlias')
```

## Current available functions
`public getDataverseInformation(alias: string): Promise<AxiosResponse> {`

`public listDatasets(alias: string): Promise<AxiosResponse> {`

`public search(options: SearchOptions): Promise<AxiosResponse> {`

`public getFile(fileId: string): Promise<AxiosResponse> {`

`public getFileMetadata(fileId: string, draftVersion: boolean = false): Promise<AxiosResponse> {`

`public getLatestDatasetInformation(datasetId: string): Promise<AxiosResponse> {`

`public async getDatasetVersions(datasetId: string): Promise<AxiosResponse> {`

```
public async getDatasetVersion(datasetId: string, version: string): Promise<AxiosResponse> {

Note: Version must be published, e.g.:
http://demo.dataverse.org/api/datasets/389608/versions/1
```

`public listDataverseRoleAssignments(dataverseAlias: string): Promise<AxiosResponse> {`

`public async getMetric(datasetId: string, metricType: DataverseMetricType, yearMonth?: string): Promise<AxiosResponse> {`

`public async getMetricByCountry(datasetId: string, metricType: DataverseMetricType, countryCode?: string, yearMonth?: string) {`

`private async getRequest(url: string, options: { params?: object, headers?: DataverseHeaders } = { headers: this.getHeaders() }): Promise<AxiosResponse> {`

## Unit Tests

### Running tests in CICD pipeline

`yarn test:ci` or `npm run test:ci`

### Test coverage

`yarn test:coverage` or `npm run test:coverage`

## Format checks
Making sure that the code format is following the guidelines

`yarn format:check` or `npm run format:check`

## Lint checks
Running a linting check on the code

`yarn eslint:check` or `npm run eslint:check`

## Contributing
[If you are interested in contributing, please click here](/CONTRIBUTING.md)