import pygame

def main():
    pygame.init()
    
    screen = pygame.display.set_mode((640,480))
    pygame.display.set_caption("Spheal")
    
    spheal = pygame.image.load("picture(1).png")
    spheal = spheal.convert_alpha()
    spheal = pygame.transform.scale(spheal, (100, 100))
    
    background = pygame.image.load("picture2.png")
    background.convert()
    background = pygame.transform.scale(background, (640,480))
    
    picture = pygame.Surface((100, 100))

    spheal_x = 0
    spheal_y = 330
    
    clock = pygame.time.Clock()
    keepGoing = True
    while keepGoing:
        clock.tick(30)
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                keepGoing = False
                
        spheal_x += 5
        if spheal_x > screen.get_width():
            spheal_x = 0
            
        screen.blit(background, (0, 0))
        screen.blit(spheal, (spheal_x, spheal_y))
        pygame.display.flip()
    
    pygame.quit()

if __name__ == "__main__":
    main()
