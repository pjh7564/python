import os           # 운영체제 관련 기능을 제공 (디렉토리 생성, 경로 결합 등)
import glob         # 파일 경로 패턴 검색 (와일드카드 사용 가능)
import shutil       # 파일 복사 및 이동 기능 제공

# 다운로드 폴더 경로 설정
downloads_dir = r'c:\Users\park\Downloads'

# 파일을 분류하여 이동시킬 대상 폴더 경로 설정
images_dir = os.path.join(downloads_dir, 'Images')      # 이미지 파일 저장 폴더
pdfs_dir = os.path.join(downloads_dir, 'PDFs')          # PDF 파일 저장 폴더
datasets_dir = os.path.join(downloads_dir, 'DataSets')  # 데이터셋 파일 저장 폴더
archives_dir = os.path.join(downloads_dir, 'Archives')  # 압축 파일 저장 폴더

# 대상 폴더들이 없으면 생성
os.makedirs(images_dir, exist_ok=True)
os.makedirs(pdfs_dir, exist_ok=True)
os.makedirs(datasets_dir, exist_ok=True)
os.makedirs(archives_dir, exist_ok=True)

# 파일 확장자 패턴과 해당 확장자를 저장할 폴더 매핑
file_patterns = {
    '*.jpeg': images_dir,
    '*.jpg': images_dir,
    '*.JPEG': images_dir,
    '*.JPG': images_dir,
    '*.pdf': pdfs_dir,
    '*.csv': datasets_dir,
    '*.tsv': datasets_dir,
    '*.xlsx': datasets_dir,
    '*.zip': archives_dir
}

# 지정된 패턴에 따라 파일들을 해당 폴더로 이동
for pattern, dest_dir in file_patterns.items():
    # 다운로드 폴더에서 해당 확장자의 파일들을 검색
    for file_path in glob.glob(os.path.join(downloads_dir, pattern)):
        try:
            # 해당 파일을 지정된 폴더로 이동
            shutil.move(file_path, dest_dir)
            print(f'Moved {file_path} to {dest_dir}')  # 이동 완료 메시지 출력
        except Exception as e:
            # 오류 발생 시 메시지 출력
            print(f'Error moving file {file_path}: {e}')
