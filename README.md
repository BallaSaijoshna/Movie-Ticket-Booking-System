public class Movie {

    private int movieId;
    private String movieName;
    private String showTime;
    private int totalSeats;
    private int availableSeats;

    // Constructor
    public Movie(int movieId, String movieName, String showTime, int totalSeats) {
        this.movieId = movieId;
        this.movieName = movieName;
        this.showTime = showTime;
        this.totalSeats = totalSeats;
        this.availableSeats = totalSeats;
    }

    // Getters
    public int getMovieId() {
        return movieId;
    }

    public String getMovieName() {
        return movieName;
    }

    public String getShowTime() {
        return showTime;
    }

    public int getTotalSeats() {
        return totalSeats;
    }

    public int getAvailableSeats() {
        return availableSeats;
    }

    // Book Seats
    public boolean bookSeats(int seats) {
        if (seats <= availableSeats) {
            availableSeats -= seats;
            return true;
        }
        return false;
    }

    // Cancel Seats
    public void cancelSeats(int seats) {
        availableSeats += seats;

        if (availableSeats > totalSeats) {
            availableSeats = totalSeats;
        }
    }

    // Display Movie Details
    public void displayMovie() {
        System.out.println("--------------------------------------");
        System.out.println("Movie ID       : " + movieId);
        System.out.println("Movie Name     : " + movieName);
        System.out.println("Show Time      : " + showTime);
        System.out.println("Total Seats    : " + totalSeats);
        System.out.println("Available Seats: " + availableSeats);
        System.out.println("--------------------------------------");
    }
}
