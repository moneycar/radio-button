import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class RadioButtonDemo extends JFrame implements ActionListener {
    private JRadioButton birdButton, catButton, dogButton, rabbitButton, pigButton;
    private JLabel petImageLabel;
    private JButton showButton;

    public RadioButtonDemo() {
        setTitle("RadioButtonDemo");
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new GridLayout(3, 2));

        // Create radio buttons
        birdButton = new JRadioButton("Bird");
        catButton = new JRadioButton("Cat");
        dogButton = new JRadioButton("Dog");
        rabbitButton = new JRadioButton("Rabbit");
        pigButton = new JRadioButton("Pig");

        // Create button group to ensure only one radio button can be selected
        ButtonGroup buttonGroup = new ButtonGroup();
        buttonGroup.add(birdButton);
        buttonGroup.add(catButton);
        buttonGroup.add(dogButton);
        buttonGroup.add(rabbitButton);
        buttonGroup.add(pigButton);

        // Create label to display pet image
        petImageLabel = new JLabel();

        // Create button to show selected pet
        showButton = new JButton("Show Pet");
        showButton.addActionListener(this);

        // Add components to the frame
        add(birdButton);
        add(catButton);
        add(dogButton);
        add(rabbitButton);
        add(pigButton);
        add(petImageLabel);
        add(showButton);

        pack();
        setVisible(true);
    }

    public void actionPerformed(ActionEvent e) {
        if (e.getSource() == showButton) {
            String selectedPet = "";
            if (birdButton.isSelected()) {
                selectedPet = "Bird";
                petImageLabel.setIcon(new ImageIcon("bird.jpg"));
            } else if (catButton.isSelected()) {
                selectedPet = "Cat";
                petImageLabel.setIcon(new ImageIcon("cat.jpg"));
            } else if (dogButton.isSelected()) {
                selectedPet = "Dog";
                petImageLabel.setIcon(new ImageIcon("dog.jpg"));
            } else if (rabbitButton.isSelected()) {
                selectedPet = "Rabbit";
                petImageLabel.setIcon(new ImageIcon("rabbit.jpg"));
            } else if (pigButton.isSelected()) {
                selectedPet = "Pig";
                petImageLabel.setIcon(new ImageIcon("pig.jpg"));
            }

            JOptionPane.showMessageDialog(this, "You selected: " + selectedPet);
        }
    }

    public static void main(String[] args) {
        new RadioButtonDemo();
    }
}# radio-button
