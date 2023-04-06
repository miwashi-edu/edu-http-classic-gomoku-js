# edu-http-classic-gomoku-js

## Expected time 6:30 minutest

## Info

In this part we will attempt to find requrements for our value-objects. We use a mockup of the game to try to determine what data is required to display a game trough it different states from create to end.

## Instructions

![mockup](./resources/mockup_1.png)

## ./__tests__/unit_tests.js

´´´js
/**
 * @group unit
 */

const gameHandler = require('../domain/gomoku.js'); // Objekt under test

/**
 * Test testing a game object returned by createGame has all
 * necessary attributes.
 */
describe('given gameHandler', () => {
  describe('when creating a game ', () => {
    const game = gameHandler.createGame();
    it('should have expected properties', () => {
      expect(game).toHaveProperty('id');
      expect(game).toHaveProperty('name');
      expect(game).toHaveProperty('round');
      expect(game).toHaveProperty('player1');
      expect(game).toHaveProperty('player2');
      expect(game).toHaveProperty('player');
      expect(game).toHaveProperty('state');
    });
  });
});
```

### Test it

The test might fail as unit_tests.js contains no tests.

```bash
code .
npm run test:watch  
```
