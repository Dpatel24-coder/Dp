import pygame

pygame.init()

# Set up the window
window_size = (800, 600)
screen = pygame.display.set_mode(window_size)

# Load images
player_image = pygame.image.load("player.png")
enemy_image = pygame.image.load("enemy.png")

# Set up player and enemy positions
player_pos = [400, 500]
enemy_pos = [400, 100]

# Game loop
running = True
while running:
    # Handle events
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    # Move player
    keys = pygame.key.get_pressed()
    if keys[pygame.K_LEFT]:
        player_pos[0] -= 5
    if keys[pygame.K_RIGHT]:
        player_pos[0] += 5
    if keys[pygame.K_UP]:
        player_pos[1] -= 5
    if keys[pygame.K_DOWN]:
        player_pos[1] += 5

    # Draw the game
    screen.fill((255, 255, 255))
    screen.blit(player_image, player_pos)
    screen.blit(enemy_image, enemy_pos)
    pygame.display.update()

pygame.quit()

