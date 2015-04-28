# Buble-sort
#Sorting via buble method

param ( $theArray = @() )

# False when swaps occur
[bool] $sorted = $false
$counter = 0
for ($pass = 1; ($pass -lt $theArray.Count) -and -not $sorted; $pass++)
{
	# Array which should be sorted
	$sorted = $true
	for ($index = 0; $index -lt ($theArray.Count - $pass); $index++)
	{
		$counter++
		$nextIndex = $index + 1
		if ($theArray[$index].CompareTo($theArray[$nextIndex]) -gt 0)
		{
			# Mixing items
			$temp = $theArray[$index]
			$theArray[$index] = $theArray[$nextIndex]
			$theArray[$nextIndex] = $temp
			$sorted = $false
		}
	}
}

Write-Host "Array items: `t" $theArray.Count
Write-Host "Iterations: `t" $counter
