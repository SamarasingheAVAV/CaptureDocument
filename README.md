# Secure Document Capture

Secure Document Capture is an Android application developed as part of an academic cybersecurity project. The application provides a controlled method for capturing sensitive documents directly through the mobile device camera and securely storing the captured images.

The main purpose of the application is to reduce the risks associated with uploading previously saved or potentially modified document images by requiring documents to be captured directly through the application.

## Features

- Live document capture using the Android Camera2 API
- No gallery or file-manager upload option
- Document type selection before capture
- Blur detection using OpenCV
- Brightness validation using OpenCV
- Retake option when image quality is unacceptable
- Photo review before storage
- Secure application-private storage
- Encryption of captured document images
- Document metadata storage
- View securely stored documents
- Designed for controlled document collection

## Supported Document Types

The application can be used to capture documents such as:

- National Identity Card (NIC)
- Driving Licence
- Vehicle registration documents
- Financial documents
- Certificates
- Other required verification documents

## Technologies Used

- Android Studio
- Kotlin
- Android Camera2 API
- OpenCV 4.10.0
- Android application-private storage
- Android security and cryptographic APIs

## Image Quality Validation

Before accepting a captured image, the application performs basic quality checks using OpenCV.

### Blur Detection

The captured image is converted to grayscale and analyzed using the Laplacian method. The calculated Laplacian variance is used to determine whether the image is sufficiently sharp.

If the image is too blurry, the user is requested to capture the document again.

### Brightness Detection

The application calculates the average grayscale brightness of the captured image.

Images that are too dark or too bright are rejected, and the user is requested to recapture the document.

## Application Flow

1. User selects the required document type.
2. The secure camera interface is opened.
3. The user captures the physical document.
4. The application checks image sharpness and brightness.
5. Images that fail the quality checks must be recaptured.
6. A successful image is displayed for review.
7. The user selects **Use Photo**.
8. The document is encrypted and stored securely.
9. Document metadata is recorded.
10. Stored documents can be accessed through the application's secure document interface.

## Security Considerations

The application is designed with security in mind by:

- Preventing document selection from the device gallery
- Capturing documents directly through the application
- Keeping captured documents within application-controlled storage
- Encrypting stored document images
- Performing image quality validation before accepting documents
- Reducing unnecessary exposure of sensitive documents

## Current Development Status

Implemented:

- Camera2 live camera capture
- Document selection
- Blur detection
- Brightness detection
- Image review and retake
- Secure encrypted storage
- Document metadata handling
- Secure document viewing

Planned / Future Improvements:

- Automatic document boundary detection
- Automatic document cropping
- Perspective correction
- Improved document alignment validation
- Additional capture quality checks

## Project Structure

Key components include:

- `CaptureActivity.kt` - Camera capture and image quality validation
- `DocumentSelectionActivity.kt` - Document type selection
- `DocumentQualityChecker.kt` - Blur and brightness validation
- `SecureStorage.kt` - Secure document storage
- `SecureDocumentsActivity.kt` - Access to stored documents
- `OpenCVInitializer.kt` - OpenCV initialization

## Requirements

- Android 8.0 (API 26) or later
- Android device with a camera
- Camera permission
- Android Studio
- Kotlin
- OpenCV

## Academic Purpose

This project was developed for academic purposes as part of a cybersecurity-related university project.

The application demonstrates secure mobile document capture, image quality validation, controlled storage, and security-focused Android development practices.

## Disclaimer

This application is an academic prototype. Additional security testing, device compatibility testing, privacy assessment, and production hardening would be required before deployment in a real-world environment.
