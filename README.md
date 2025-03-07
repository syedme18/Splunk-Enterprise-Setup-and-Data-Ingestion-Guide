# Splunk-Enterprise-Setup-and-Data-Ingestion

## Installing Splunk Enterprise Free Trial

### Step 1: Download Splunk Enterprise
1. Open your browser and go to [Splunk.com](https://www.splunk.com/).
2. Click on **Products** and select **Free Trials & Downloads**.  
   ![1](https://github.com/user-attachments/assets/1f3e6900-f48e-4704-bf46-6ca56264b45f)

3. You will see two platform options:
   - **Splunk Cloud**: 5GB/day for 14 days.
   - **Splunk Enterprise** (will be using): 500MB/day for 60 days.
4. Under **Splunk Enterprise**, click **Get My Free Trial**.  
   ![2](https://github.com/user-attachments/assets/d8f4376a-0d2d-484e-9716-eb02f83b18b3)

5. Fill out the registration form.  
   - Use your college email ID (or preferred email).
6. Click **Create My Account** and verify your email via the link sent by Splunk.

### Step 2: Install Splunk Enterprise
1. After verification, you will receive a download link.  
   ![4](https://github.com/user-attachments/assets/745dce1b-463d-4d2a-8d0c-6bb2a98d1e00)

2. Sign in and download Splunk Enterprise for your OS (Windows/Linux/macOS).
3. Click **Download Now** to begin downloading.
4. Once downloaded, start the installation process.
5. Accept the license agreement.  
   ![6](https://github.com/user-attachments/assets/bea649c5-2505-403d-9563-2f78d3b08c4e)

6. Enter your **username and password**, then proceed with installation.  
   ![7](https://github.com/user-attachments/assets/da14d02c-8632-4429-aa50-f6610759fe9a)


### Step 3: Logging into Splunk Enterprise
1. Open Splunk by visiting `http://localhost:8000`.
2. Login using your credentials.  
   ![8](https://github.com/user-attachments/assets/adaaca3e-dc21-4dae-a8b1-8fc791780244)

3. You will now see the **Splunk Dashboard**.  
   ![9](https://github.com/user-attachments/assets/840cef2d-b13e-40c6-8daf-b841fe17b070)


---

## Ingesting Data into Splunk

### Method 1: Uploading a CSV File
1. Go to **Settings → Add Data**.  
   ![10](https://github.com/user-attachments/assets/225a2a7c-dcb5-403c-98d2-885a87666a2c)

2. Click on **Upload**.  
   ![11](https://github.com/user-attachments/assets/19ea4a33-c00b-40a8-b1b1-b8f48cb22d5a)

3. Select your **CSV file** and upload.
4. Click **Next**, and Splunk will show a preview of the data.  
   ![12](https://github.com/user-attachments/assets/5d55003a-4869-4098-b8b3-69e4d7b9efc5)

5. Click **Next**, then configure the index:
   - Create a **new index** (e.g., `apps` for Windows Event Logs).  
   ![13](https://github.com/user-attachments/assets/b44f2a93-a8dd-4433-9e4a-b1d0518cd5ea)

   - Leave the event type as **Event**.
   - Click **Save**.  
     ![14](https://github.com/user-attachments/assets/81624fca-df51-46c7-9043-0cbdd51b5a51)

6. Click **Review and Submit** to complete data ingestion.  
   ![15](https://github.com/user-attachments/assets/4aa1fa70-73dc-4e1b-9450-3d95ec3fcba2)


### Searching the Ingested Data
1. Go to the **Dashboard** and enter the search query:
   ```
   index="apps"
   ```
2. Click **Search** to display results (e.g., 59,426 events).  
   ![16](https://github.com/user-attachments/assets/1528fd1d-4e06-4f24-a9af-e2baa4e4afa4)

3. Filter data using fields like:
   - **Event ID**
   - **Date, Month, Minute** (from the left panel)  
   ![17](https://github.com/user-attachments/assets/3dc62903-bf00-4a76-acdb-19ba7193719a)

4. Use the **time filter** (top-right) to view logs in **Real-time, Last 24 hours, All time**, etc.  
   ![18](https://github.com/user-attachments/assets/403fb23c-ddad-4b65-8e8d-a6367fb684ca)
   <br>
   ![19](https://github.com/user-attachments/assets/081782d1-da90-4e2c-8984-dc57fd8d82fd)



### Method 2: Ingesting Data Using Universal Forwarder
The **Universal Forwarder** is a lightweight Splunk agent that collects and sends logs from remote machines to the Splunk indexer.

#### Step 1: Download Splunk Universal Forwarder
- Download it from [Splunk Forwarder](https://www.splunk.com/en_us/download/universal-forwarder.html).

#### Step 2: Configure Receiving in Splunk Enterprise
1. In **Splunk Enterprise**, go to **Add Data**.
2. Click **Forwarding and Receiving**.  
   ![20](https://github.com/user-attachments/assets/f6d0658d-db93-4b62-9231-c1cda5ebd935)

3. Under **Receiving Data**, click **Configure Receiving**.  
   ![21](https://github.com/user-attachments/assets/edebe3a5-cbbe-414c-9a49-ab2db06867fb)

4. Click **New Receiving Port** and enter `9997`.

#### Step 3: Install and Configure the Forwarder on Windows
1. Run the Universal Forwarder installer and select **Customize**.  
   ![22](https://github.com/user-attachments/assets/c312671c-efd0-44ca-9497-d123885a4dc1)

2. Choose **Local System**, then click **Next**.
3. Select the events you want to ingest.  
   ![23](https://github.com/user-attachments/assets/da277376-6972-4d66-8139-da5b6ddd4bb0)

4. Enter your **username and password**, then click **Next**.
5. Enter the **Splunk host IP** and the **Receiving Port (`9997`)**.  
   ![24](https://github.com/user-attachments/assets/58e089d0-12cc-4548-aeac-9e12134d0b36)

6. Click **Install**.

#### Step 4: Verify Data in Splunk Enterprise
1. Go to **Splunk Enterprise**.
2. Click **Forwarder Management**.
3. The machine where the forwarder is installed should now appear.

---

## Conclusion
This guide covers:
- Installing **Splunk Enterprise**
- Ingesting data via **CSV upload**
- Setting up **Universal Forwarder** for remote log collection

Now you can explore Splunk for searching, monitoring, and analyzing data efficiently!

