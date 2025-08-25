# surratt-csc256-repo

This is my repository for my Software Quality Assurance class. Also known as CSC256 in the Fall 2025 term. ==This repository will include all projects for this class.==

### Projects:
1. None so far

#### Example Code that I've written
```
    def generate_password():
        old_codes = load_past_codes()
        show_old_codes(old_codes)

        alphanum = ('ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz'
                    '1234567890!@#$%^&*')

        random.seed(time.time())
        length_of_code = secrets.choice(range(11, 24))

        while True:
            generate = input('Generate a code? (y/n): ')
            if generate.lower() == 'y':
                code = ''.join(random.choice(alphanum) for _ in range(length_of_code))
                current_date = datetime.datetime.now().strftime('%Y-%m-%d %H:%M:%S')
                print("New {}-character code: {} (Generated {})".format(length_of_code, code, current_date))

                if isinstance(old_codes, list):
                    old_codes.append({"Code":code, "Generated": current_date})
                    save_past_codes(old_codes)
                    show_old_codes(old_codes)
                else:
                    print('error')

            elif generate.lower() == 'n':
                sys.exit()
            else:
                print('type y or n')
```