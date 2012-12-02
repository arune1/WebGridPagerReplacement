#WebMatrix WebGrid Pager Replacement
This class allows you to replace the standard pager element of the WebMatrix WebGrid with a new version that allows it to be styled with [Twitter Bootstrap](http://twitter.github.com/bootstrap/index.html).

Check out the blog post [here](http://www.mdobie.co.uk/2012/12/02/webmatrix-webgrid-re-working-the-pager/).

##Usage
Add the class to the `App_Code` directory.

Initialize the grid at the top of your webpage like normal

    WebGrid grid = new WebGrid(source)

To render the table with the new pager you need call them separately, this will render the grid and a list (ul / li) pager below.

	@grid.Table(
	    columns: grid.Columns(
	        ...
        )
    )
    @grid.PagerList(mode: WebGridPagerModes.All)


To render the pager with Bootstrap styling add in the additional classes

	@grid.Table(
	    tableStyle: "table table-striped table-hover",
	    columns: grid.Columns(
	        ...
	    )
	)
	<div class="pagination pagination-small pagination-right">
	    @grid.PagerList(mode: WebGridPagerModes.All)
	</div> 