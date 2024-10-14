---
{"dg-publish":true,"permalink":"/drexel-perforce/perforce-streams/virtual-streams/","noteIcon":""}
---

### Step 1: Understanding Virtual Streams

Virtual streams in Perforce allow you to create a filtered view of a real stream, providing the capability to work with a subset of files without syncing unnecessary content. This is especially useful for:

- Submitting changes directly to a stream.
- Developing with different sets of libraries across multiple platforms.

### Step 2: Creating a Virtual Stream

**A. Open the Stream Editor:**

- Navigate to the Stream Graph in P4V.
- Right-click on the stream where you want to create a virtual stream and select "**Create New Stream from 'stream name'…**".

**B. Configure the Stream Type:**

- In the Stream dialog that appears, go to the Basic Settings tab.
- Select the stream type "virtual - used to narrow the scope and submit directly to the parent".

**C. Define the Paths:**

- On the Advanced tab, specify the paths that define what to include or exclude in your virtual stream. Use:
    - `Share ...` : Paths included with shared are shared with the parent stream. Meaning merging/copying/branching/submitting are not allowed by default. This action takes place in the parent stream, but files added or deleted from a shared path automatically propagate to the parent.
        - ``` share path/to/diredctory/... ```
    - `exclude ...` to exclude everything by default. Always behaves as exclusion. Paths included here are excluded from view or actions.
        - ```exclude paht/to/directory/...```
    - `isolate` or `import` paths in a virtual stream, in most cases, essentially act as `share` does.

### Step 3: Finalizing Your Virtual Stream

- Review your path settings to ensure they meet your needs.
- Click "OK" to create the virtual stream.

### Step 4: Working with Virtual Streams

**A. Submitting Changes:**

- Changes made in a virtual stream can be submitted directly to its parent stream. This setup avoids the need for merging changes from child streams to parent streams.

**B. Visual Indicators in Streams Graph:**

- Virtual streams are depicted with a dashed border and connected to their parent streams with a gray line. This representation shows that they filter content from the parent without the typical merge or copy paths.

### Step 5: Stream Path Behavior

Understand how different path types behave in a virtual stream:

- **Share:** Includes files for viewing and syncing but does not allow submitting or branching.
- **Isolate:** Similar to share but used to signify files that are isolated from typical development processes.
- **Import:** Allows files from other locations to be viewed and synced, behaving like share when importing from the parent.
- **Exclude:** Removes files or directories from the stream view entirely.

### Step 6: Managing Copies and Merges

While you can manage copies and merges directly through real streams, any operations through virtual streams affect only their base parent. This setup simplifies the handling of changes and ensures that modifications are applied where intended.

---
# Helix Core Official Documentation on Virtual Streams
- Video - https://www.perforce.com/video-tutorials/vcs/using-virtual-streams 
-  Written - https://www.perforce.com/manuals/p4v/Content/P4V/streams.virtual.html