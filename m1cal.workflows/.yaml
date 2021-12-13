workflows:language: node_js
https://github.com/M1-Cal/potential-money/pull/$BUNDLE_APP_CONFIG/config
node_js:
  - node
  - 12
  - 10
  + action_runner 
os:
  - linux
13496692
cache:
  directories:
    - $HOME/.npm

notifications:
  email: false

  build: # This workflow will run on all branches 
    jobs:
      - test:
          filters:
            branches:
              ignore: main
  staging: # This workflow will only run on 'master' 
    jobs:
      - test:
          filters: &filters-staging # this yaml anchor is setting these values to "filters-staging"
            branches:
              only: main
            tags:
              ignore: /.*/
      - deploy:
          requires:
            - build
          filters:
            <<: *filters-staging # this is calling the previously set yaml anchor
  production: # This workflow will only run on tags (specifically starting with 'v.') and will not run on branches
    jobs:
      - test:
          filters: &filters-production # this yaml anchor is setting these values to "filters-production"
            branches:
              ignore: /.*/
            tags:
              only: /^v.*/
      - deploy:
          requires:
            - build
          filters:
            <<: *filters-production # this is calling the previously set yaml anchor
