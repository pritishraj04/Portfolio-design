<script>
  import Icon from "@iconify/svelte";
  import mailIcon from "@iconify/icons-bytesize/mail.js";
  import phoneIcon from "@iconify/icons-bi/phone.js";
  import githubOutlineFill from "@iconify/icons-akar-icons/github-outline-fill.js";
  import linkedinOutlined from "@iconify/icons-ant-design/linkedin-outlined.js";
</script>

<main>
  <h1>Get in touch with me</h1>
  <p class="info">Average response time: 48 Hrs.</p>
  <section class="contact">
    <div class="contact-data">
      <div class="single-contact">
        <Icon width={30} icon={mailIcon} />
        <a href="mailto:pritishraj04@gmail.com">pritishraj04@gmail.com</a>
      </div>
      <div class="single-contact">
        <Icon width={30} icon={phoneIcon} />
        <a href="tel:+919097785207">+91-9097785207</a>
      </div>
      <div class="single-contact">
        <Icon width={30} icon={githubOutlineFill} />
        <a
          href="https://www.github.com/pritishraj04"
          target="_blank"
          rel="noopener noreferrer">github.com/pritishraj04</a
        >
      </div>
      <div class="single-contact">
        <Icon width={30} icon={linkedinOutlined} />
        <a
          href="https://www.linkedin.com/in/pritishraj04"
          target="_blank"
          rel="noopener noreferrer">linkedin.com/in/pritishraj04</a
        >
      </div>
    </div>
    <form>
      <div class="form-group">
        <label for="name"> Name </label>
        <input
          type="text"
          id="name"
          name="name"
          placeholder="Enter your name here."
        />
      </div>
      <div class="form-group">
        <label for="email"> Email </label>
        <input
          type="email"
          id="email"
          name="email"
          placeholder="Enter your email here."
        />
      </div>
      <div class="form-group">
        <label for="category"> Category </label>
        <select name="category" id="category">
          <option value="bussines">Bussines</option>
          <option value="personal">Personal</option>
          <option value="hiring">Hiring</option>
          <option value="chat">Chat</option>
        </select>
      </div>
      <div class="form-group">
        <label for="comments"> Comments </label>
        <textarea
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
  </section>
</main>

<style lang="scss">
  main {
    margin-top: 2rem;
    h1 {
      font-weight: 400;
      font-size: clamp(1.6rem, 2.2vw, 3.125rem);
    }
    .info {
      margin-bottom: 2rem;
      font-size: clamp(0.6rem, 1vw, 1.5rem);
    }
    a {
      font-size: clamp(0.8rem, 1.2vw, 1.925rem);
    }
    .contact {
      display: grid;
      grid-template-columns: 2.8fr 1fr;
      column-gap: 2rem;
      grid-row: auto;
      @media only screen and (max-width: 768px) {
        grid-template-columns: 1fr;
      }
      .contact-data {
        order: 1;
        margin-bottom: 2rem;
        @media only screen and (max-width: 768px) {
          order: 0;
        }
        .single-contact {
          display: flex;
          align-items: center;
          margin-top: 0.5rem;
          gap: 1rem;
          &:first-child {
            margin-top: 0;
          }
        }
      }
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
    }
  }
</style>
