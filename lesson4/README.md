# 前提
* 診療科ごとに対応可能な診療内容がある。
* 医師ごとに対応可能な診療内容がある。

# テーブル説明

## receptions
受付情報を管理するテーブル。

患者は `patient_id` で参照し、会計番号を `accounting_number`、受付日時を `received_at` に保存する。

## details
受付ごとの診察明細を管理するテーブル。

受付は `reception_id`、診療科は `department_id`、診療内容は `examination_id`、担当医師は `doctor_id` で参照する。診察時刻は `examined_at` に保存する。

## patients
患者情報を管理するテーブル。

患者コードを `code`、患者名を `name` に保存する。

## departments
診療科を管理するテーブル。

診療科名を `name` に保存する。

## department_purposes
診療科と診療内容の対応関係を管理する中間テーブル。

診療科は `department_id`、診療内容は `examination_id` で参照する。

## examinations
診療内容を管理するテーブル。

診療内容名を `name` に保存する。

## doctor_purposes
医師と診療内容の対応関係を管理する中間テーブル。

医師は `doctor_id`、診療内容は `examination_id` で参照する。

## doctors
医師情報を管理するテーブル。

医師名を `name` に保存する。