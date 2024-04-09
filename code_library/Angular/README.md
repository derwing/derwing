# Code you can use in Angular (test in v9)

## rating
<p align="left">
This code show a full, medium or half star base on the rating - When the average rating is receive as a float number.
</p>

### HTML
<code>
    <div class="star-rating">
        <!-- Loop through each star based on the Product/Service average Rating -->
        <i *ngFor="let star of getStars(averageRating); let i = index" class="{{ star }}"></i>
    </div>
</code>

### TypeScript
<code>
  getStars(averageRating: number) {
    // Array to store the classes of stars
    const stars = [];
    // Loop through each star (5 stars in total)
    for (let i = 1; i <= 5; i++) {
      // If the rating is greater than the current star index,
      // it means the star should be filled (full star)
      if (rating > i) {
        stars.push('fas fa-star text-warning'); // Add class for filled star
      }
      // If the rating is greater than the previous star index,
      // but less than or equal to the current star index,
      // it means the star should be half-filled
      else if (rating > i - 1) {
        stars.push('fas fa-star-half-alt text-warning'); // Add class for half-filled star
      }
      // If the rating is less than or equal to the current star index,
      // it means the star should be empty
      else {
        stars.push('far fa-star text-warning'); // Add class for empty star
      }
    }

    // Return the array of star classes
    return stars;
  }
</code>

### Result
example averageRating = 2.8
<img align="right" width="350" src="/code_library/assets/rating.png" alt="Coding gif" />
  
