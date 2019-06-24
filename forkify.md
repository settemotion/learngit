# forkify笔记

## webpack 安装 配置

### npm install webpack --save-dev 
配置文件：webpack.config.js

const path = require('path');
module.exports = {
    entry:\['./src/js/index.js],
    output: {
        path: path.resolve(__dirname, 'dist'),
        filename: 'js/bundle.js'
    }
}

### npm install webpack-cli --save-dev

### npm install webpack-dev-server --save-dev

### npm install html-webpack-plugin --save-dev

### npm install babel-core babel-preset-env babel-loader --save-dev

## axios babel-polyfill 

## 其他要点

### hashchange
window.addEventListener('hashchange', controlRecipe);
const controlRecipe = () => {
    const id = window.location.hash.replace('#', '');
    
    if(id) {
        ......
        
    }
}

### e.target.match  e.target.closet

else if(e.target.matches('.btn-increase, .btn-increase *')) {
        //increase serving
        state.recipe.updateServing('inc');
        recipeView.updateServingIngredients(state.recipe);
    } 
    
const id = e.target.closest('.shopping__item').dataset.itemid;

const btn = e.target.closest('.btn-inline');
    if (btn) {
        const gotoPage = parseInt(btn.dataset.goto, 10);
        searchView.clearResults();
        searchView.renderResults(state.search.result, gotoPage);
    }
    
### 在markup 中再markup

\<div class="recipe__ingredients">
        \<ul class="recipe__ingredient-list">
            ${recipe.ingredients.map(el => createIngredient(el)).join('')}
        \</ul>
                
        const createIngredient = ingredient => `
    <li class="recipe__item">
        <svg class="recipe__icon">
            <use href="img/icons.svg#icon-check"></use>
        </svg>
        <div class="recipe__count">${formatCount(ingredient.count)}</div>
        <div class="recipe__ingredient">
            <span class="recipe__unit">${ingredient.unit}</span>
            ${ingredient.ingredient}
        </div>
    </li>
`;