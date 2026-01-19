# 1.a.Implementation-of-Go-Back-N-protocol-Sliding-window
learners are instructed to submit the details 
🎯 AIM
To write and execute a program for the Go-Back-N protocol.

🖥️ Equipments Required
Personal Computer

Turbo C Compiler

⚙️ Procedure
Connect two computers in Wired/Wireless LAN.

Ensure both computers are in the same network and can ping each other.

In Code::Blocks, open a new C file and type the program.

From the menu: Project → Properties → Project Build Options → Linker Settings → Add netproto and pthread.

Execute the program on both server and client.

Enter the IP address of the remote machine, port address of both local & remote machine, and error rate.

Choose the file and verify the Go-Back-N protocol operation.

📄 Program


#include <stdio.h>
/* Assume 7 frames of data are to be sent using GO BACK N ARQ */
#define window_size 4

void main() {
    int i, window_start = 1, ack;
    int n;

    printf("SLIDING WINDOW PROTOCOL\n");
    printf("GO BACK N ARQ\n");

    printf("Enter the number of frames: ");
    scanf("%d", &n);

    char frame[n+1][10];

    for (i = 1; i <= n; i++) {
        printf("Content for frame %d: ", i);
        scanf("%s", frame[i]);
    }

    while (window_start <= n) {
        printf("\nSending frames...\n");
        printf("Enter frame number with no ACK (0 if all acknowledged): ");
        scanf("%d", &ack);

        if (ack == 0) {
            printf("All frames acknowledged. Moving window forward.\n");
            window_start += window_size;
        } else {
            printf("No Acknowledgement for frame %d...\n", ack);
            printf("Resending frames starting from frame %d\n", ack);
            window_start = ack;
        }
    }

    printf("\nAll frames sent successfully.\n");
}
🖥️ Sample Output
"C:\Users\ASUS\OneDrive\Pictures\Screenshots 1\7a.png"
✅ Result
Thus, the Go-Back-N protocol (Sliding Window) was implemented and the output was verified successfully.
