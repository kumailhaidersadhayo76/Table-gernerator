import javax.crypto.Cipher;
import javax.swing.*;
import javax.swing.border.BevelBorder;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class Table2 extends JFrame{
    public Table2(){

        setSize(400,400);
        setTitle("|--Table--|");


        JTextField t = new JTextField();
        t.setBounds(100,20,100,25);

        JLabel l = new JLabel("Table:");
        l.setBounds(100, 70, 50, 10);
        l.setBackground(Color.white);

        JTextArea t2 = new JTextArea();
        t2.setBounds(100,100,100,160);
        t2.setEditable(false);

        JButton b = new JButton("Enter");
        b.setBounds(210,20,80,25);
        b.setBackground(Color.gray);
        b.setForeground(Color.white);
        
        b.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                int x = Integer.parseInt(t.getText());
                StringBuilder tab = new StringBuilder();
                for(int a=1; a<=10;a++){
                    int r = a*x;
                    tab.append(x).append("  x  ").append(a).append("  =  ").append(r).append("\n");
                }
                t2.setText(tab.toString());

            }
        });



        setLayout(null);
        setVisible(true);
        add(t);
        add(b);
        add(l);
        add(t2);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
    }

    public static void main(String[] args) {
        new Table2();
    }
}