# Create the final zip file with updated content
final_zip_path = "/mnt/data/Palwasha_Birthday_Surprise_Final.zip"

with ZipFile(final_zip_path, "w") as zipf:
    for foldername, subfolders, filenames in os.walk(folder_path):
        for filename in filenames:
            file_path = os.path.join(foldername, filename)
            arcname = os.path.relpath(file_path, folder_path)
            zipf.write(file_path, arcname)

final_zip_path
