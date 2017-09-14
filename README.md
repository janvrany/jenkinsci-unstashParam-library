# JENKINS-27413 workaround library

This [pipeline library][2] contains a workaround for Jenkins issue [ JENKINS-27413][1]. It provides a new step `unstashParam` that saves file parameter to a workspace.

## Configuration

See [Jenkins User Handbook, chapter Extending with Shared Libraries][2] on how to configure pipeline libraries.

## Usage

In a pipeline script:

    library "JENKINS-27413-workaround-library"
    node {
       def file_in_workspace = unstashParam "file"
       sh "cat ${file_in_workspace}"
    }

The above assumes the Jenkins job has a file build parameter named `file`.

## License

This library is MIT licensed. See `license.txt` for details.

[1]: https://issues.jenkins-ci.org/browse/JENKINS-27413
[2]: https://jenkins.io/doc/book/pipeline/shared-libraries/
