# My Favorite *Clean Code* Chapter Is Only Six Pages Long

I “reread” *Clean Code*, the well-known book in which Robert “Uncle Bob” C. Martin and his colleagues at Object Mentor share what they consider the best practices for making code clean, understandable, and maintainable.

I put “reread” in quotation marks because the first time I read the book was in 2012—twelve years before this article was published. In a way, it felt like reading it for the first time.

I was able to understand some things back then, but the second reading was valuable because it showed me the origins of practices I have applied and shared through tacit knowledge after a little over a decade in the software development industry.

It also helped me move beyond some of the common clichés surrounding the book. It was particularly interesting to revisit the authors' guidance on topics such as boundaries between systems, concurrency, and even how to be a more conscientious and professional programmer. That last topic is explored further in another book, *The Clean Coder*.

However, the chapter that stood out most to me was Chapter 12, written by Jeff Langr. It covers the emergence of software systems and conveys the essence of the book in only six pages. It is important to clarify that “emergence” in the chapter title does not refer to urgency, but to something emerging or evolving.

The chapter offers a compelling perspective on what to watch for when building systems that can grow sustainably. I strongly believe the central goal of every programmer should be to deliver experiences and products that create a competitive advantage and meet customer needs. Building a high-quality system that is easy to maintain and evolve is essential to achieving that competitiveness with an appropriate time to market.

Another point that greatly helps us deliver quality software quickly—and one I consider a major priority—is ensuring that a change in one software layer does not break or affect the others. Here, *Clean Code* works alongside techniques such as Hexagonal Architecture and design patterns, but this chapter remains a foundation for reaching that level. Ultimately, every technique we apply serves this purpose.

## The Four Rules of Simple Design

The chapter presents Kent Beck's “Four Rules of Simple Design”:

1. **Pass all tests.** We need to ensure that our code behaves as expected, and a comprehensive, well-written unit test suite helps us verify that. Moreover, if the system needs refactoring, tests ensure that changes have not broken what was already working. Test code is as important as production code and should not be negotiable. Shipping something without tests because it is “faster” is paid amateurism. If someone asks for a deployment without tests—typically under extreme pressure—we need to have difficult conversations about it.
2. **Avoid code duplication.** Also known as the DRY principle: Don't Repeat Yourself. Repeating code across multiple components creates unnecessary risks, affects delivery time, and can increase project costs. If only one of the duplicated locations is changed and the others are forgotten, errors are inevitable.
3. **Express intent.** This is where the book's best-known and most discussed guidance comes into play: use meaningful names, small and expressive functions, and classes with a single responsibility that are designed for extension. In short, another programmer should be able to read your code and understand, at least broadly, what you intended to express.
4. **Minimize the number of classes and functions.** Keep the number of classes and methods as small as necessary, while staying alert to avoid pointless dogmatism—for example, always creating an interface for every class being written.

In summary, this chapter gives us a true north for what to consider when building genuinely clean code. It is a useful reference for deciding what we should study to improve the cleanliness and quality of our code. If I had absorbed and practiced these ideas more deeply after my first reading, I certainly would not have gone through certain difficulties and crises. Scars are important, but learning from the experience of others is valuable too.

`#cleancode` `#book` `#softwaredevelopment`
