/POST
/bo-room/repos/{owner}/{repo}/check-runs
{
  {
    
}
curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <YOUR-TOKEN>" \
  -H "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/repos/OWNER/REPO/check-runs \
  -d '{"name":"mighty_readme","head_sha":"ce587453ced02b1526dfb4cb910479d431683101","status":"completed","started_at":"2017-11-30T19:39:10Z","conclusion":"success","completed_at":"2017-11-30T19:49:10Z","output":{"title":"Mighty Readme report","summary":"There are 0 failures, 2 warnings, and 1 notices.","text":"You may have some misspelled words on lines 2 and 4. You also may want to add a section in your README about how to install your app.","annotations":[{"path":"README.md","annotation_level":"warning","title":"Spell Checker","message":"Check your spelling for '\''banaas'\''.","raw_details":"Do you mean '\''bananas'\'' or '\''banana'\''?","start_line":2,"end_line":2},{"path":"README.md","annotation_level":"warning","title":"Spell Checker","message":"Check your spelling for '\''aples'\''","raw_details":"Do you mean '\''apples'\'' or '\''Naples'\''","start_line":4,"end_line":4}],"images":[{"alt":"Super bananas","image_url":"http://example.com/images/42"}]},"actions":![-eqh4z2](https://github.com/room-bo/room-bo/assets/140757544/6a0eed63-13b6-45fa-8525-5f6ef09acefc)
[{"label":"Fix","identifier":"fix_errors","description":"Allow us to fix these errors for you"}]}'
  
  
// Octokit.js
// https://github.com/octokit/core.js#readme
const octokit = new Octokit({
  auth: 'YOUR-TOKEN'
})

await octokit.request('POST /repos/{owner}/{repo}/check-runs', {
  owner: 'OWNER',
  repo: 'REPO',
  name: 'mighty_readme',
  head_sha: 'ce587453ced02b1526dfb4cb910479d431683101',
  status: 'completed',
  started_at: '2017-11-30T19:39:10Z',
  conclusion: 'success',
  completed_at: '2017-11-30T19:49:10Z',
  output: {
    title: 'Mighty Readme report',
    summary: 'There are 0 failures, 2 warnings, and 1 notices.',
    text: 'You may have some misspelled words on lines 2 and 4. You also may want to add a section in your README about how to install your app.',
    annotations: [
      {
        path: 'README.md',
        annotation_level: 'warning',
        title: 'Spell Checker',
        message: 'Check your spelling for \'banaas\'.',
        raw_details: 'Do you mean \'bananas\' or \'banana\'?',
        start_line: 2,
        end_line: 2
      },
      {
        path: 'README.md',
        annotation_level: 'warning',
        title: 'Spell Checker',
        message: 'Check your spelling for \'aples\'',
        raw_details: 'Do you mean \'apples\' or \'Naples\'',
        start_line: 4,
        end_line: 4
      }
    ],
    images: [
      {
      
        alt: 'Super bananas',
        image_url: 'http://example.com/images/42'
      }
    ]
  },
  actions: [
    {
      label: 'Fix',
      identifier: 'fix_errors',
      description: 'Allow us to fix these errors for you'
    }
  ],
  headers: {
    'X-GitHub-Api-Version': '2022-11-28'
  }
})
