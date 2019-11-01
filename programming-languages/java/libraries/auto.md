# [Google Auto](https://github.com/google/auto)

- Using AutoValue with JSON serde

  ```java
	@AutoValue
	@JsonSerialize(as = Member.class)
	@JsonDeserialize(builder = Member.Builder.class)
	public abstract class Member {

			@JsonProperty("id")
			public abstract Integer memberId();

			@JsonProperty("bidder_id")
			public abstract Integer bidderId();

			@JsonProperty("active")
			public abstract Boolean active();

			@AutoValue.Builder
			@JsonIgnoreProperties(ignoreUnknown = true)
			public static abstract class Builder {

					@JsonCreator
					public static Member.Builder builder() {
							return new AutoValue_Member.Builder();
					}

					public abstract Member build();

					@JsonProperty("id")
					public abstract Member.Builder memberId(final Integer memberId);

					@JsonProperty("bidder_id")
					public abstract Member.Builder bidderId(final Integer bidderId);

					@JsonProperty("active")
					public abstract Member.Builder active(final Boolean active);
			}

	}
  ```
