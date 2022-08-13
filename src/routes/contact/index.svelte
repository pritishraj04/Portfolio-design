<form
  name="contact"
  action="/contact/success"
  method="POST"
  data-netlify="true"
  data-netlify-honeypot="bot-field"
>
  <input type="hidden" name="form-name" value="contact" />
  <p hidden>
    <label>
      Don't fill this out: <input name="bot-field" />
    </label>
  </p>
  <div class="form-group">
    <label for="name"> Name </label>
    <input
      type="text"
      required
      id="name"
      name="name"
      placeholder="Enter your name here."
    />
  </div>
  <div class="form-group">
    <label for="email"> Email </label>
    <input
      type="email"
      required
      id="email"
      name="email"
      placeholder="Enter your email here."
    />
  </div>
  <div class="form-group">
    <label for="category"> Category </label>
    <select name="category" id="category">
      <option value="personal">Personal</option>
      <option value="bussines">Talk bussines</option>
      <option value="project">Related to Listed Projects</option>
      <option value="hiring">Want to Hire</option>
      <option value="chat">Friendly Chat</option>
    </select>
  </div>
  <div class="form-group">
    <label for="comments"> Comments </label>
    <textarea
      required
      type="comments"
      id="comments"
      name="comments"
      rows="8"
      placeholder="Enter your comments here."
    />
  </div>
  <div class="form-group">
    <input type="submit" id="submit" />
  </div>
</form>

<style lang="scss">
  form {
    .form-group {
      margin-bottom: 1rem;
      label {
        display: block;
        font-size: clamp(0.8rem, 1.2vw, 1.925rem);
        margin-bottom: 0.2rem;
      }
      input,
      textarea,
      select {
        width: 100%;
        color: var(--clr-primary-text);
        background: hsla(0, 0%, 100%, 0.25);
        font-size: clamp(0.8rem, 1.1vw, 1.7rem);
        padding: 0.6rem 0.4rem;
        border: none;
        &:focus {
          outline: var(--clr-primary-link-hvr) 2px solid;
        }
        &::placeholder {
          color: hsla(0, 0%, 100%, 0.377);
        }
      }
      textarea {
        max-width: 100%;
        resize: vertical;
      }
      select {
        background: hsla(0, 0%, 100%, 0.39);
        option {
          color: black;
        }
      }
      #submit {
        font-weight: 600;
        color: var(--clr-primary-link-hvr);
        background: var(--clr-secondary-bg);
        &:hover {
          color: var(--clr-primary-bg);
          background: var(--clr-primary-comp);
        }
      }
    }
  }
</style>
