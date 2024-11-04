import socket


def url_to_ip(url):
    try:
        ip_address = socket.gethostbyname(url)
        return ip_address
    except socket.gaierror:
        return "Invalid URL or unable to resolve IP."


def ip_to_url(ip):
    try:
        url = socket.gethostbyaddr(ip)[0]
        return url
    except socket.herror:
        return "Invalid IP address or unable to resolve URL."


def menu():
    print("\nDNS Lookup Menu")
    print("1. Get IP address from UR11L")
    print("2. Get URL from IP address")
    print("3. Exit")


while True:
    menu()
    choice = input("Enter your choice (1/2/3): ")

    if choice == '1':
        url = input("Enter the URL: ")
        ip_address = url_to_ip(url)
        print(f"IP Address: {ip_address}")

    elif choice == '2':
        ip = input("Enter the IP address: ")
        url = ip_to_url(ip)
        print(f"URL: {url}")

    elif choice == '3':
        print("Exiting the program.")
        break

    else:
        print("Invalid choice! Please choose 1, 2, or 3.")
