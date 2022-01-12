
```
provider "aws" {
    alias = "us-west-2"
    region = "us-west-2"
}

provider "aws" {
    alias = "us-east-1"
    region = "us-east-1"
}

resource "aws_sns_topic" "topic_us_east" {
    provider = aws.us-east-1
    name = "topic-us-east"
}

resource "aws_sns_topic" "topic-us-west" {
    provider = aws.us-west-2
    name = "topic-us-west"
}

```