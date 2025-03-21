import openai

openai.api_key = "کلید-API-شما"

def generate_code(prompt):
    response = openai.ChatCompletion.create(
        model="gpt-4",
        messages=[{"role": "user", "content": prompt}]
    )
    return response["choices"][0]["content"]

user_prompt = input("چه چیزی می‌خواهی در برنامه‌ات بنویسی؟ ") or "چاپ Hello World"
generated_code = generate_code(f"یک برنامه پایتون برای {user_prompt} بنویس")

print("\nکد پیشنهادی AI:\n")
print(generated_code)
