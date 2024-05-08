package application;
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Label;
import javafx.scene.control.ListView;
import javafx.scene.control.ScrollPane;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.HBox;
import javafx.scene.layout.StackPane;
import javafx.scene.paint.Color;
import javafx.scene.shape.Rectangle;
import javafx.stage.Stage;
import javafx.collections.FXCollections;

public class Main extends Application {

    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        primaryStage.setTitle("LISTA DE MIS AMIGOS DE LA UNI");

        BorderPane root = new BorderPane();

        ListView<StackPane> leftListView = new ListView<>();
        leftListView.setItems(FXCollections.observableArrayList(
                createLabeledBox("  STEVEN BENTACOURT", new Image("https://i.pinimg.com/236x/14/b3/ac/14b3ac636ef69e40805a22505b41605b.jpg")),
                createLabeledBox("  HEIDY PANCHANA", new Image("https://i.pinimg.com/750x/65/4b/95/654b954997b39739d49ed2f21aae84df.jpg")),
                createLabeledBox("  CARLOS LINO", new Image("https://i.pinimg.com/564x/60/53/9b/60539bc9844fa25d8369706e7314e771.jpg")),
                createLabeledBox("  JANDY SANCHEZ", new Image("https://i.pinimg.com/564x/fc/ae/1d/fcae1dad207e973656c70f4284c625eb.jpg")),
                createLabeledBox("  DANNA GARCÍA", new Image("https://img.wattpad.com/5c1b29ccb153404755d7bf69169325ab1d7e4d24/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f776174747061642d6d656469612d736572766963652f53746f7279496d6167652f444751354b6a574a6a53586130773d3d2d3134392e313633396133323332386264626432623132313137383931343733352e6a7067?s=fit&w=720&h=720")),
                createLabeledBox("  DUA LIPA", new Image("https://i.ytimg.com/vi/N000qglmmY0/maxresdefault.jpg"))

        ));
        leftListView.setPrefSize(300, 300);

        ScrollPane leftScrollPane = new ScrollPane(leftListView);
        leftScrollPane.setFitToWidth(true);
        leftScrollPane.setVbarPolicy(ScrollPane.ScrollBarPolicy.ALWAYS);
        leftScrollPane.setHbarPolicy(ScrollPane.ScrollBarPolicy.NEVER);

        // Crear dos rectángulos negros dentro del color azul
        Rectangle blueRectangle1 = new Rectangle(200, 400);
        blueRectangle1.setFill(Color.BLUE);

        Rectangle blueRectangle2 = new Rectangle(200, 400);
        blueRectangle2.setFill(Color.BLUE);

        // Aplicar los rectángulos azules en StackPane
        StackPane blueStackPane1 = new StackPane(blueRectangle1);
        StackPane blueStackPane2 = new StackPane(blueRectangle2);

        // Aplicar los ListView y los StackPane azules en un HBox
        HBox hbox = new HBox(leftScrollPane, blueStackPane1, blueStackPane2);

        root.setCenter(hbox);

        Scene scene = new Scene(root, 700, 300);
        primaryStage.setScene(scene);
        primaryStage.show();
    }

    private StackPane createLabeledBox(String labelText, Image image) {
        Label label = new Label(labelText);

        ImageView imageView = new ImageView(image);
        imageView.setFitWidth(20);
        imageView.setFitHeight(20);

        HBox hBox = new HBox();
        hBox.getChildren().addAll(imageView, label);

        StackPane stackPane = new StackPane();
        stackPane.getChildren().add(hBox);
        return stackPane;
    }
}

![image](https://github.com/BetancourtSteven/BetancourtSteven.io/assets/169225554/225360c1-c0a2-4aa4-b4f2-7fa882c371a9)
