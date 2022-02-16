---
title: Microsoft Managed Desktop の操作と監視
description: Who変更プロセスに対して何を行う
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
ms.openlocfilehash: 6b1771660cb25ccd9d23c97d1e3fcf6edd27feaa
ms.sourcegitcommit: 559df2c86a7822463ce0597140537bab260c746a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2022
ms.locfileid: "62825223"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft Managed Desktop の操作と監視

<!-- Operations and monitoring: -->

## <a name="change-management"></a>変更管理

サービス提供では、ハードウェアメンテナンスとセキュリティ更新プログラムの責任のバランスが、顧客 (お客様) ではなくサービス プロバイダー (Microsoft) に移行します。 ただし、更新プログラムの展開時に Microsoft 以外のソフトウェアとカスタム ソフトウェアが引き続き期待通り機能し続ける必要があります。

オンプレミス製品の場合、組織は変更を管理する責任を負います。

### <a name="balance-of-responsibility"></a>責任のバランス

| 責任 | Microsoft Managed Desktop サービス | Microsoft 365 クライアント ソフトウェア | オンプレミスのクライアントとサーバー | Microsoft 以外のソフトウェアとカスタム ソフトウェア
| ----- | ----- | ----- | ----- | ----- |
| 新しい機能の提供 | Microsoft | Microsoft | Both/フォーム/データシート | 顧客
| 品質保証のための新機能のテスト |  Microsoft | Microsoft | Both/フォーム/データシート | 顧客
| 新機能についての通信 | Both/フォーム/データシート | Both/フォーム/データシート | Both/フォーム/データシート | 顧客
| カスタム ソフトウェアの統合 | Both/フォーム/データシート | Both/フォーム/データシート | 顧客 | 顧客
| セキュリティ更新プログラムの適用 | Microsoft | Microsoft | 顧客 | 顧客
| システム ソフトウェアの保守 | Microsoft | Microsoft | 顧客 | 顧客
| 展開用パッケージ | Microsoft | Microsoft | 顧客 | 顧客

### <a name="change-process-overview"></a>変更プロセスの概要

以下に、Microsoft と顧客の間で変更プロセスを共有する方法の概要を示します。

| シナリオ | Microsoft の役割 | お客様の役割 |
| ----- | ----- | ----- |
| 変更前 | <ul><li>サービス変更に関する予測を設定します。</li><li>管理者の操作が必要な変更については、5 日前に顧客に通知します。</li><li>緊急の変更については、通知する前に軽減策を適用してください。</li></ul> | <ul><li>変更と通信に関して予想されていることを理解します。</li><li>Microsoft Managed Desktop Message Center を定期的に読む。</li><li>内部の変更管理プロセスを確認して更新します。</li><li>Microsoft Managed Desktop の要件に準拠していることを理解し、確認します。 </li><li>必要に応じて、確認と承認を行います。</li></ul>
| 変更中 | <ul><li>クライアントとクライアントのセキュリティとセキュリティ以外の更新プログラムを毎月リリースWindows 10展開Office 365します。</li><li>データ信号を監視し、影響を受け取るキューをサポートします。</li></ul> | <ul><li>Microsoft Managed Desktop Message Center を確認し、その他の情報を確認します。</li><li>必要なアクション (該当する場合) を実行し、アプリケーションをテストします。</li><li>ブレーク/修正シナリオが発生した場合は、サポート要求を作成します。</li></ul> |
| 変更後 | <ul><li>今後の変更のロールアウトを改善するために、顧客からのフィードバックを収集します。</li><li>データ信号を監視し、影響を受け取るキューをサポートします。</li></ul> | <ul><li>組織内のユーザーと一緒に作業し、変更を採用します。</li><li>変更管理プロセスと導入管理プロセスを確認して、効率を高める機会を得る。</li><li>管理者フィードバック ツールで、一般的なフィードバックと特定のフィードバックを提供します。</li><li>ユーザーがアプリ固有のフィードバックを提供するには、Windows フィードバック Hubアプリの [スマイル] ボタンOfficeします。</li></ul> |

### <a name="change-types"></a>変更の種類

サービスに対して定期的に行う変更には、いくつかの種類があります。 これらの変更の通信チャネルと、担当するアクションはさまざまです。

すべての変更がユーザーに同じ影響を与える場合や、アクションが必要な場合はありません。 一部は計画済みで、一部は計画外です。 たとえば、セキュリティ以外の更新プログラムとセキュリティ更新プログラムは、通常は計画されません。

変更の種類によっては、通信チャネルが異なる場合があります。 次の表に、Microsoft Managed Desktop サービスで期待できる変更の種類を示します。

|  | 機能 | セキュリティ以外の更新プログラム | セキュリティ |
| ----- | ----- | ----- | ----- |
| **変更の種類** | <ul><li>機能の更新</li><li>新機能またはアプリケーション</li><li>推奨されない機能</li></ul> | 問題に関するクライアント修正プログラム | セキュリティ更新プログラム |
**事前通知** | アクションが必要な変更に関する 5 日間の通知 | このような変更は、月次リリースに含まれません | 月次リリースに変更は含まれません |
**通信チャネル** | <ul><li>メッセージ センター</li><li>電子メールアラート</li></ul> | <ul><li>メッセージ センター</li><li>電子メールアラート</li></ul> | <ul><li>メッセージ センター</li><li>電子メールアラート</li></ul> |
**グローバル管理者の操作が必要** | 時々 | まれに | まれに |
**アクションの種類** | 設定の変更 | ユーザーへの変更の伝達 | 管理設定の変更 |
**テストが必要** | リモート アクセス サービスを含むビジネス アプリケーションを確認する | 場合によっては、次の場合があります。プロセスまたはカスタマイズに対する修正プログラムのテスト | まれに |
**変更の例** | <ul><li>機能更新プログラム: IT 管理者ポータルによるサポート チケットの提出とレビューの簡略化</li><li>新機能またはアプリケーション: Semi-Annual機能更新プログラムWindows 10リリース</li></ul> | お客様によって報告されたバグに基づく修正プログラム |

## <a name="standard-operating-procedures"></a>標準的な操作手順

Microsoft Managed Desktop サービスは、Microsoft クラウド インスタンスで Microsoft によって実装および運用され、他の管理アクティビティを行う可能性があります。 Microsoft は、Microsoft Managed Desktop 固有のセットアップ、構成、および操作の責任を負います。

オンプレミス製品の場合、組織はセットアップ、および構成と運用のアクティビティを管理する責任を負います。

| カテゴリ | Microsoft は、 | お客様は、 |
| ----- | ----- | ----- |
| ネットワーク (プロキシ、パケット 検査、VPN) | ビジネス ユーザーに対するリスクを最小限に抑えるために、お客様にアドバイスを提供し、計画します。 | <ul><li>計画された構成変更に関する情報を要求するサポート要求を作成します。 Microsoft が確認する構成の詳細、スコープ、タイムライン、その他の関連する詳細を含める。</li><li>Microsoft Managed Desktop Operations が評価およびアドバイスを行った後にのみ、変更を適用します。</li></ul> |
サービス アカウント | <ul><li>資格情報の実装、安全な保存、管理を行います。</li><li>これらの資格情報の不正なアクセスまたは使用をセキュリティ運用チームに伝えます。</li></ul> | <ul><li>計画された構成変更に関する情報を要求するサポート要求を作成します。 Microsoft が確認する構成の詳細、スコープ、タイムライン、その他の関連する詳細を含める。</li><li>Microsoft Managed Desktop Operations が評価およびアドバイスを行った後にのみ、変更を適用します。</li><li>ポリシー、多要素認証、条件付きアクセス、またはアプリケーションの展開を Microsoft Managed Desktop Service アカウントに割り当てない。</li><li>パスワードをリセットしたり、資格情報を使用したりしない。</li><li>これらのサービス アカウントに関連する Intune または Azure 監査ログで疑わしいアクティビティが観察された場合は、Microsoft Managed Desktop Operations に対する Sev C サポート要求を開きます。</li></ul>
| デバイス グループ | <li> Microsoft Managed Desktop グループ内のデバイスのメンバーシップを実装して割り当てる。</li><li>Microsoft Managed Desktop グループを使用して、デバイスへの構成と更新プログラムの割り当てとリリースを管理します。</li></ul> | <ul><li>計画された構成変更に関する情報を要求するサポート要求を作成します。 Microsoft が確認する構成の詳細、スコープ、タイムライン、その他の関連する詳細を含める。</li><li>Microsoft Managed Desktop Operations が評価およびアドバイスを行った後にのみ、変更を適用します。</li><li>「デバイスを展開グループに割り当てる」で説明されている手順に従って、Microsoft Managed Desktop グループにのみデバイス [を割り当てる必要があります](../working-with-managed-desktop/assign-deployment-group.md)。</li><li>グループを使用して、VPN、ビジネスまたは電子メールの暗号化Windows Hello、企業の Wifi プロファイル構成などのサービスに企業証明書を割り当てる必要があります。</li><li>共同管理が存在する場合は、Configuration Manager クライアントを展開するときに、すべての Microsoft 管理デスクトップ グループを明示的に除外します。</li></ul>
| ポリシー | <ul><li>サービス内のデバイスの構成状態を管理する Microsoft Managed Desktop ポリシーを実装および管理します。</li><li> デバイス グループを使用して段階的にWindowsポリシーまたはポリシーに更新プログラムを展開します。</li><li>Microsoft Managed Desktop 以外のグループを対象として明示的に除外します。</li></ul> | <ul><li>計画された構成変更に関する情報を要求するサポート要求を作成します。 Microsoft が確認する構成の詳細、スコープ、タイムライン、その他の関連する詳細を含める。</li><li>Microsoft Managed Desktop Operations が評価およびアドバイスを行った後にのみ、変更を適用します。</li><li>Microsoft Managed Desktop サービスによって管理されていないデバイスまたはユーザーに、Microsoft Managed Desktop ポリシーを編集または割り当てない。
Microsoft 365 Defenderエンドポイントの場合。</li></ul> | Microsoft Managed Desktop サービスのスコープ内のデバイスを監視および調査します。 | <ul><li>計画された構成変更に関する情報を要求するサポート要求を作成します。 Microsoft が確認する構成の詳細、スコープ、タイムライン、その他の関連する詳細を含める。</li><li>Microsoft Managed Desktop Operations が評価およびアドバイスを行った後にのみ、変更を適用します。</li></ul>
| ビジネス向け Microsoft Store | Microsoft Managed Desktop サービスWindowsプロファイルを構成および管理します。 | <ul><li>計画された構成変更に関する情報を要求するサポート要求を作成します。 Microsoft が確認する構成の詳細、スコープ、タイムライン、その他の関連する詳細を含める。</li><li>Microsoft Managed Desktop Operations が評価およびアドバイスを行った後にのみ、変更を適用します。</li><li>Microsoft Managed Desktop プロファイルの構成を変更しないWindows割り当てられたデバイスを追加または削除します。</li></ul>
| 証明書 | | <ul><li>証明書の有効期限の 60 日前にサポート 要求を作成し、計画された構成変更の情報を要求します。 Microsoft が確認する構成の詳細、スコープ、タイムライン、その他の関連する詳細を含める。</li><li>Microsoft Managed Desktop Operations が評価およびアドバイスを行った後にのみ、変更を適用します。</li><li>証明書プロファイル、VPN プロファイル、および証明書プロファイルを構成するために必要なすべての証明書Wi-Fiします。</li></ul>|

## <a name="device-wipe-with-factory-reset"></a>工場出荷時の状態にリセットされたデバイスワイプ

Microsoft Managed Desktop Operations チームは、必要に応じて、サービスに登録されているデバイスの出荷時のリセットを実行できます。 リセットは、別の従業員にデバイスを提供する必要がある場合、または従業員が会社を離れる場合に役立ちます。

いくつかの要件があります。

- グローバル管理者は、サポート要求を送信する必要があります。
- 要求にデバイスのコンピューター名を含める。
- デバイスをリセットする前にAzure ADアカウントがインストールされている必要があります。

管理デスクトップ操作チームは次の作業を行います。

- Intune でデバイス名を検索します。
- 出荷時のリセット コマンドをデバイスに送信します。

> [!NOTE]
> デバイスがリセットされる前に、Azure ADアカウントを削除しない。 ユーザーがデバイスにAzure AD場合、Intune は出荷時のリセット コマンドをデバイスに送信できません。

デバイスは"箱から出たエクスペリエンス" で起動し、プレインストールされているアプリケーションと設定はすべて再び適用されます。 デバイスのユーザーは、初期セットアップ情報を再度提供する必要があります。

デバイスがリセットされた場合は、組織内の別のユーザーにデバイスを提供できます。 前のユーザーのデータまたはエンタープライズ データはいずれもデバイス上に存在しない。 次のユーザーは、前のユーザーが新しい Microsoft マネージ デスクトップ デバイスで行ったのと同じプロセスを実行します。

BitLocker は、このプロセスのデータ セキュリティの重要なコンポーネントです。 Microsoft Managed Desktop デバイスでの BitLocker 暗号化では、デバイスが工場出荷時の状態にリセットされた後でも、ドライブ上のデータは安全に維持されます。 ドライブ上に保存されたデータは、デバイスの次のユーザーが使用できません。 詳細については、「 [BitLocker の概要」を参照してください](/windows/security/information-protection/bitlocker/bitlocker-overview)。

詳細については、「デバイスを出荷時 [にリセットする」を参照してください](/intune/remote-actions/devices-wipe#factory-reset-a-device)。
