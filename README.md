import pygame
import sys

# Initialize pygame
pygame.init()

# Screen settings
WIDTH, HEIGHT = 800, 600
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Motorbike Game")

# Colors
WHITE = (255, 255, 255)
BLACK = (0, 0, 0)

# Load motorbike image
motorbike_img = pygame.image.load("motorbike.png")
motorbike_rect = motorbike_img.get_rect(center=(WIDTH // 2, HEIGHT - 100))

# Motorbike movement settings
speed_x = 5
speed_y = 0

# Main game loop
clock = pygame.time.Clock()
running = True
while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    # Movement controls
    keys = pygame.key.get_pressed()
    if keys[pygame.K_LEFT] and motorbike_rect.left > 0:
        motorbike_rect.x -= speed_x
    if keys[pygame.K_RIGHT] and motorbike_rect.right < WIDTH:
        motorbike_rect.x += speed_x

    # Fill the screen
    screen.fill(WHITE)

    # Draw the motorbike
    screen.blit(motorbike_img, motorbike_rect)

    # Update the screen
    pygame.display.flip()
    clock.tick(30)  # Limit FPS to 30

<!---
activatermaddy/activatermaddy is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
