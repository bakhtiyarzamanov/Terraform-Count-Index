# Terraform-Count-Index
Use count.index and replace the hard-coded values.


main.tf
resource "local_file" "name" {
    filename = var.users[count.index]
    sensitive_content = var.content
    count = length(var.users)

}

variable.tf

variable "users" {
    type = list
}
variable "content" {
    default = "password: S3cr3tP@ssw0rd"
  
}

