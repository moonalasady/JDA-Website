import java.util.Scanner;
import net.dv8tion.jda.api.JDA;
import net.dv8tion.jda.api.JDABuilder;
import net.dv8tion.jda.api.events.message.MessageReceivedEvent;
import net.dv8tion.jda.api.hooks.ListenerAdapter;

public class DiscordBot extends ListenerAdapter {

  public static void main(String[] args) throws Exception {
    JDA jda = new JDABuilder("MTA1ODA4MzgxNjk1NjI0ODE3NA.GljQlY.KXHcXBHo-6coFA1qtmGTOFMtgnazYZnOiM45yE").build();
    jda.addEventListener(new DiscordBot());
  }

  @Override
  public void onMessageReceived(MessageReceivedEvent event) {
    if (event.getAuthor().isBot()) return;
    String message = event.getMessage().getContentRaw();
    if (message.equals("مرحبا")) {
      event.getChannel().sendMessage("هل تحتاج لمساعدة؟").queue();
    }
  }
}
