---
swagger: "2.0"
x-collection-name: MasterCard
x-complete: 0
info:
  title: Mastercard Get Block
  description: |-
    By default, this call returns the last confirmed block, since the `from`
    and `to` parameters will both default to the last confirmed slot number.
    To get a range of blocks, use the `from` and `to` parameters. Specifying
    only the `from` parameter will get a range of blocks up to the current slot.
    Note that this also means that specifying `to` without `from` will result
    in an error since that will mean a negative range.

    For each returned item, the data will contain header information from
    the block binary, and references to the block entries via the merkle roots.

    Note that the maximum range request allowed is 600 entries.
  version: 1.0.0
host: eas5stl0.mastercard.int:13046
basePath: /z0/core/v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /block:
    get:
      summary: Get Block
      description: |-
        By default, this call returns the last confirmed block, since the `from`
        and `to` parameters will both default to the last confirmed slot number.
        To get a range of blocks, use the `from` and `to` parameters. Specifying
        only the `from` parameter will get a range of blocks up to the current slot.
        Note that this also means that specifying `to` without `from` will result
        in an error since that will mean a negative range.

        For each returned item, the data will contain header information from
        the block binary, and references to the block entries via the merkle roots.

        Note that the maximum range request allowed is 600 entries.
      operationId: getBlock
      x-api-path-slug: block-get
      parameters:
      - in: query
        name: from
        description: Specify the starting slot to return
      - in: header
        name: MCWSSAML
        description: SAML Authorization
      - in: query
        name: to
        description: Specify the last slot to return
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Block
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---