# Connecting to AWS with PuTTY
1. Start PuTTY
    * From the **Start** menu, choose **All Programs -> PuTTY -> PuTTY**
2. In the **Category** pane, choose **Session** and complete the fields:
    * In the **Host Name** box, enter `ec2-user@public_dns_name`. Where `public_dns_name` is the IPv4 asssociated with the ec2 instance. (This process is detailed in the [General Windows Prerequisites](./Windows/WinGenRequisites/WinGenRequisites.md)).
    * Under **Connection type**, select **SSH**.
    * Ensure that the **Port** value is **22**.
3. *IMPORTANT*: Configure PuTTY to automatically send `keepalive` data at regular intervals to keep the session active. This is useful to avoid disconnecting from your instance while MaxEnt runs. In the **Category** pane, choose **Connection**, and then enter the required interval, **30**, in the S**econds between keepalives** field.
4. In the **Category** pane, expand **Connection**, expand **SSH**, and then choose **Auth**. Complete the following:
    * Choose **Browse**.
    * Select the `.ppk` file that you generated for your key pair and choose Open.
    * (Optional) If you plan to start this session again later, you can save the session information for future use. Under **Category**, choose **Session**, enter a name for the session in **Saved Sessions**, and then choose **Save**.
    * Choose **Open**.
5. If this is the first time you have connected to this instance, PuTTY displays a security alert dialog box that asks whether you trust the host to which you are connecting.
6. Choose **Yes**. A window opens and you are now connected to your instance. You may now Procede to run MaxEnt Setup if this is the first time connecting to the instance.
