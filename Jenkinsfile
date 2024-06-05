pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/NUCESFAST/scd-final-lab-exam-sheraztariq22.git'
            }
        }

        stage('Install Dependencies') {
            parallel {
                stage('Auth') {
                    steps {
                        dir('Auth') {
                            sh 'npm install'
                        }
                    }
                }

                stage('Classroom') {
                    steps {
                        dir('Classrooms') {
                            sh 'npm install'
                        }
                    }
                }

                stage('Event-Bus') {
                    steps {
                        dir('event-bus') {
                            sh 'npm install'
                        }
                    }
                }

                stage('Post') {
                    steps {
                        dir('Post') {
                            sh 'npm install'
                        }
                    }
                }

                stage('Clinet') {
                    steps {
                        dir('client') {
                            sh 'npm install'
                        }
                    }
                }
            }
        }

        stage('Build Docker Images') {
            parallel {
                stage('Auth') {
                    steps {
                        dir('Auth') {
                            sh "docker build -t sheraztariq22/auth:latest ."
                        }
                    }
                }

                stage('Classroom') {
                    steps {
                        dir('Classrooms') {
                            sh "docker build -t sheraztariq22/classroom:latest ."
                        }
                    }
                }

                stage('Event-Bus') {
                    steps {
                        dir('event-bus') {
                            sh "docker build -t sheraztariq22/event-bus:latest ."
                        }
                    }
                }

                stage('Post') {
                    steps {
                        dir('Post') {
                            sh "docker build -t sheraztariq22/post:latest ."
                        }
                    }
                }

                stage('Client') {
                    steps {
                        dir('client') {
                            sh "docker build -t sheraztariq22/client:latest ."
                        }
                    }
                }
            }

        }

        stage('Push Docker Images to Docker Hub') {
            parallel {
                stage('Auth') {
                    steps {
                        dir('Auth') {
                            sh "docker push sheraztariq22/auth:latest"
                        }
                    }
                }

                stage('Classroom') {
                    steps {
                        dir('Classrooms') {
                            sh "docker push sheraztariq22/classroom:latest"
                        }
                    }
                }

                stage('Event-Bus') {
                    steps {
                        dir('event-bus') {
                            sh "docker push sheraztariq22/event-bus:latest"
                        }
                    }
                }

                stage('Post') {
                    steps {
                        dir('Post') {
                            sh "docker push sheraztariq22/post:latest"
                        }
                    }
                }

                stage('Client') {
                    steps {
                        dir('client') {
                            sh "docker push sheraztariq22/client:latest"
                        }
                    }
                }
            }
        }

    }
}
