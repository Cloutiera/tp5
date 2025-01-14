
"""
Modèle de départ pour la programmation Arcade.
Il suffit de modifier les méthodes nécessaires à votre jeu.
"""
import arcade

SCREEN_WIDTH = 800
SCREEN_HEIGHT = 800
SCREEN_TITLE = "Ma Maison"


class MyGame(arcade.Window):
    """
    La classe principale de l'application

    NOTE: Vous pouvez effacer les méthodes que vous n'avez pas besoin.
    Si vous en avez besoin, remplacer le mot clé "pass" par votre propre code.
    """

    def __init__(self, width, height, title):
        super().__init__(width, height, title)

        # arcade.set_background_color(arcade.color.AMAZON)

        # Si vous avez des listes de sprites, il faut les créer ici et les
        # initialiser à None.

    def setup(self):
        """
        Configurer les variables de votre jeu ici. Il faut appeler la méthode une nouvelle
        fois si vous recommencer une nouvelle partie.
        """
        # C'est ici que vous allez créer vos listes de sprites et vos sprites.
        # C'est aussi ici que vous charger les sons de votre jeu.
        pass

    def on_draw(self):
        """
        C'est la méthode que Arcade invoque à chaque "frame" pour afficher les éléments
        de votre jeu à l'écran.
        """

        # Cette commande permet d'effacer l'écran avant de dessiner. Elle va dessiner l'arrière
        # plan selon la couleur spécifié avec la méthode "set_background_color".
        arcade.set_background_color(arcade.color.GRAY)
        self.clear()

        # gazon
        arcade.draw.draw_ellipse_filled(400, 100, 1000, 400, arcade.color.DARK_GREEN)
        # MAISON
        arcade.draw.draw_lrbt_rectangle_filled(200, 600, 200, 500, arcade.color.BEIGE)
        # TOIT
        arcade.draw_triangle_filled(100, 500, 700, 500, 400, 700, arcade.color.RED)
        # CHEMINEE
        arcade.draw.draw_lrbt_rectangle_filled(550, 600, 500, 670, arcade.color.RED)
        # PORTE
        arcade.draw.draw_lrbt_rectangle_filled(250, 330, 202, 350, arcade.color.BLACK)
        # fenetre cadre
        arcade.draw.draw_circle_filled(400, 570, 20, arcade.color.BROWN)
        # toit fenetre
        arcade.draw.draw_arc_filled(400, 600, 60, 20, arcade.color.GREEN, 0, 180, )
        # croix fenetre horizontal
        points_horizontal = [(380, 570), (420, 570)]

        arcade.draw.draw_line_strip(points_horizontal, arcade.color.BUFF)
        # vertical
        points_vertical = [(400, 550), (400, 590)]
        arcade.draw.draw_line_strip(points_vertical, arcade.color.BUFF)
        # fenetre de porte
        points_soleil = [(270, 290), (310, 290), (290, 330)]
        arcade.draw.draw_polygon_filled(points_soleil, arcade.color.WHITE)
        # texte
        affichage = arcade.Text("Ma maison", 300, 750, arcade.color.BARBIE_PINK, font_size=30)
        affichage.draw()

        # Invoquer la méthode "draw()" de vos sprites ici.

    def on_update(self, delta_time):
        """
        Toute la logique pour déplacer les objets de votre jeu et de
        simuler sa logique vont ici. Normalement, c'est ici que
        vous allez invoquer la méthode "update()" sur vos listes de sprites.
        Paramètre:
            - delta_time : le nombre de milliseconde depuis le dernier update.
        """
        pass

    def on_key_press(self, key, key_modifiers):
        """
        Cette méthode est invoquée à chaque fois que l'usager tape une touche
        sur le clavier.
        Paramètres:
            - key: la touche enfoncée
            - key_modifiers: est-ce que l'usager appuie sur "shift" ou "ctrl" ?

        Pour connaître la liste des touches possibles:
        http://arcade.academy/arcade.key.html
        """
        pass

    def on_key_release(self, key, key_modifiers):
        """
        Méthode invoquée à chaque fois que l'usager enlève son doigt d'une touche.
        Paramètres:
            - key: la touche relâchée
            - key_modifiers: est-ce que l'usager appuie sur "shift" ou "ctrl" ?
        """
        pass

    def on_mouse_motion(self, x, y, delta_x, delta_y):
        """
        Méthode invoquée lorsque le curseur de la souris se déplace dans la fenêtre.
        Paramètres:
            - x, y: les coordonnées de l'emplacement actuel de la sourir
            - delta_X, delta_y: le changement (x et y) depuis la dernière fois que la méthode a été invoqué.
        """
        pass

    def on_mouse_press(self, x, y, button, key_modifiers):
        """
        Méthode invoquée lorsque l'usager clique un bouton de la souris.
        Paramètres:
            - x, y: coordonnées où le bouton a été cliqué
            - button: le bouton de la souris appuyé
            - key_modifiers: est-ce que l'usager appuie sur "shift" ou "ctrl" ?
        """
        pass

    def on_mouse_release(self, x, y, button, key_modifiers):
        """
        Méthode invoquée lorsque l'usager relâche le bouton cliqué de la souris.
        Paramètres:
            - x, y: coordonnées où le bouton a été relâché
            - button: le bouton de la souris relâché
            - key_modifiers: est-ce que l'usager appuie sur "shift" ou "ctrl" ?
        """
        pass


def main():
    """ Main method """
    game = MyGame(SCREEN_WIDTH, SCREEN_HEIGHT, SCREEN_TITLE)
    game.setup()
    arcade.run()


if __name__ == "__main__":
    main()
