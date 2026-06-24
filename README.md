def create_edit_delete_file():
    folder_name = "MunnaTheDev"
    os.makedirs(folder_name, exist_ok=True)

    max_uses = 3
    uses = 0

    while uses < max_uses:
        try:
            file_name = os.path.join(
                folder_name,
                f"{generate_random_string(8)}.txt"
            )

            with open(file_name, "w") as file:
                for _ in range(random.randint(10, 100)):
                    file.write(generate_random_string(100) + "\n")
            print(f"[MunnaTheDev] Created: {file_name}")

            time.sleep(2)

            with open(file_name, "w") as file:
                for _ in range(random.randint(10, 100)):
                    file.write(generate_random_string(100) + "\n")
            print(f"[MunnaTheDev] Edited: {file_name}")

            time.sleep(1)

            os.remove(file_name)
            print(f"[MunnaTheDev] Deleted: {file_name}")

            uses += 1
            print(f"[MunnaTheDev] Use {uses}/{max_uses}")

            time.sleep(1)

        except Exception as e:
            print(f"[MunnaTheDev] An error occurred: {e}")
            time.sleep(5)

    print("\n[MunnaTheDev] Trial expired! This script can only be used 3 times.")
