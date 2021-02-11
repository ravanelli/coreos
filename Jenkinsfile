imageName = buildImage(gitURL: "https://github.com/coreos/coreos-assembler.git")
pod(image: imageName, kvm: true, memory: "10Gi") {

  shwrap("rpm -qa | sort > rpmdb.txt")
  archiveArtifacts artifacts: 'rpmdb.txt'
  
  fcosBuild(skipKola: 1, cosaDir: "/srv", noForce: 1)

} 
