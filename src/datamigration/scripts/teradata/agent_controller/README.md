# Agent Controller

A daemon service to run on agent vm to manage migration agent jobs

## Manual Installation
* Install the dependencies: `pip install -r requirements.txt`
* Create `config.yaml` file
```yaml
project_id: <project-id>
subscription_id: <agent-controller-subscription-id>
```

## Usage
`python main.py`

## Actions
1. Setup 
   * Creates transfer run directory
   * Creates credential file
   * Creates agent config file
2. Run
   * Runs migration agent for given transfer run id
3. Kill
   * Kills migration agent process


### Sample PUB/SUB Payload
Setup
```json
{
   "time": "2022-12-17T22:17:08.750674Z",
   "transfer_id": "63b3777c-0000-2ef3-ad41-94eb2c093804",
   "params": {
      "agent_config": "eyJ0cmFuc2Zlci1jb25maWd1cmF0aW9uIjogeyJwcm9qZWN0LWlkIjogIjY1MDg3OTQ3OTkyMSIsICJsb2NhdGlvbiI6ICJ1cyIsICJpZCI6ICI2M2ZiYjkwYS0wMDAwLTIwN2ItODZlYi05NGViMmMwOWQ3ZGMifSwgInNvdXJjZS10eXBlIjogInRlcmFkYXRhIiwgImNvbnNvbGUtbG9nIjogZmFsc2UsICJzaWxlbnQiOiBmYWxzZSwgInRlcmFkYXRhLWNvbmZpZyI6IHsiY29ubmVjdGlvbiI6IHsiaG9zdCI6ICIzNC4xMzYuMTU1Ljc1IiwgInVzZXJuYW1lIjogImRiYyIsICJzZWNyZXRfcmVzb3VyY2VfaWQiOiAicHJvamVjdHMvNjUwODc5NDc5OTIxL3NlY3JldHMvc2VjcmV0LWVkd19jcmVkZW50aWFsc19kYmMvdmVyc2lvbnMvMSJ9LCAibG9jYWwtcHJvY2Vzc2luZy1zcGFjZSI6ICIvb3B0L21pZ3JhdGlvbl9wcm9qZWN0X3RlcmFkYXRhX2JxL2xvY2FsX3Byb2Nlc3Npbmdfc3BhY2UiLCAibWF4LWxvY2FsLXN0b3JhZ2UiOiAiMjAwR0IiLCAiZ2NzLXVwbG9hZC1jaHVuay1zaXplIjogIjMyTUIiLCAidXNlLXRwdCI6IHRydWUsICJyZXRhaW4tdHB0LWZpbGVzIjogZmFsc2UsICJtYXgtc2Vzc2lvbnMiOiAwLCAic3Bvb2wtbW9kZSI6ICJOb1Nwb29sIiwgIm1heC1wYXJhbGxlbC11cGxvYWQiOiAyLCAibWF4LXBhcmFsbGVsLWV4dHJhY3QtdGhyZWFkcyI6IDIsICJzZXNzaW9uLWNoYXJzZXQiOiAiVVRGOCIsICJtYXgtdW5sb2FkLWZpbGUtc2l6ZSI6ICIyR0IiLCAiZGF0YWJhc2UtY3JlZGVudGlhbHMtZmlsZS1wYXRoIjogIi9vcHQvdHJhbnNmZXJfY29uZmlnc19hbmRfbG9ncy82M2ZiYjkwYS0wMDAwLTIwN2ItODZlYi05NGViMmMwOWQ3ZGMvY3JlZGVudGlhbHMifSwgImFnZW50LWlkIjogIjU2N2FjNGY0LTI1NWYtNDcyMi1iZWYxLWM4NjI1ZjdlMjNhNCJ9Cg=="
   },
   "action": "setup"
 }
```

Run
```json
{
   "time": "2022-12-17T22:17:09.750674Z",
   "transfer_id": "63b3777c-0000-2ef3-ad41-94eb2c093804",
   "params": {},
   "action": "run"
 }
```

Kill
```json
{
   "time": "2022-12-17T22:18:08.750674Z",
   "transfer_id": "63b3777c-0000-2ef3-ad41-94eb2c093804",
   "params": {},
   "action": "kill"
 }
```