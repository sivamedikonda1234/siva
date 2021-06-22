# siva
terraform code
resource "google_compute_instance" "mhr-qa" {
  name         = var.instancename
  machine_type = var.machinetype
  zone         = var.zone

 

  boot_disk {
    initialize_params {
      image = "debian-cloud/debian-9"
    }
  }

 

  network_interface {
    subnetwork = google_compute_subnetwork.subenet-mhr-hr.id

    access_config {
      // Ephemeral IP
    }
  }

}
