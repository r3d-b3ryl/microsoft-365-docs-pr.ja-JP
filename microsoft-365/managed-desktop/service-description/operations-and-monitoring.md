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
ms.openlocfilehash: 29144da5c9dffb3bfe37d8068bdbc2b56f1ab401
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034679"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft Managed Desktop の操作と監視

<!-- Operations and monitoring: -->

## <a name="change-management"></a>変更管理

サービス提供においては、ハードウェアのメンテナンスやセキュリティ更新などの責任のバランスは、お客様ではなく、サービス プロバイダー (Microsoft) に移行します。 ただし、Microsoft 以外のソフトウェアとカスタム ソフトウェアが、更新プログラムの展開時に期待通り機能し続ける必要があります。

オンプレミス製品の場合、組織は変更を管理する責任を負います。

### <a name="balance-of-responsibility"></a>責任のバランス

責任 | Microsoft Managed Desktop サービス | Microsoft 365 クライアント ソフトウェア | オンプレミスのクライアントとサーバー | Microsoft 以外のソフトウェアとカスタム ソフトウェア
----- | ----- | ----- | ----- | -----
新しい機能の提供 | Microsoft | Microsoft | Both/フォーム/データシート | 顧客
品質保証のための新機能のテスト |  Microsoft | Microsoft | Both/フォーム/データシート | 顧客
新機能についての通信 | Both/フォーム/データシート | Both/フォーム/データシート | Both/フォーム/データシート | 顧客
カスタム ソフトウェアの統合 | Both/フォーム/データシート | Both/フォーム/データシート | 顧客 | 顧客
セキュリティ更新プログラムの適用 | Microsoft | Microsoft | 顧客 | 顧客
システム ソフトウェアの保守 | Microsoft | Microsoft | 顧客 | 顧客
展開用パッケージ | Microsoft | Microsoft | 顧客 | 顧客

### <a name="change-process-overview"></a>変更プロセスの概要

Microsoft と顧客の間で変更プロセスを共有する方法の概要を次に示します。 

<table>
<tr><th></th><th><p>Microsoft の役割:</p></th><th><p>顧客の役割:</p></th></tr>
<tr><td>変更前</td><td><ul><li>サービス変更に関する予測を設定します。</li><li>管理者の操作が必要な変更については、5 日前に顧客に通知します。</li><li>緊急の変更については、通知する前に軽減策を適用してください。</li></ul></td><td><ul><li>変更と通信に関して予想されていることを理解します。</li><li>Microsoft Managed Desktop Message Center を定期的に読む。</li><li>内部の変更管理プロセスを確認して更新します。</li><li>Microsoft Managed Desktop の要件に準拠していることを理解し、確認します。 </li><li>必要に応じて、確認と承認を行います。</li></ul></td></tr><tr><td>変更中</td><td><ul><li>クライアントとクライアントのセキュリティとセキュリティ以外の更新プログラムを毎月リリースWindows 10展開Office 365します。</li><li>データ信号を監視し、影響を受け取るキューをサポートします。</li></ul></td><td><ul><li>Microsoft Managed Desktop Message Center を確認し、その他の情報を確認します。</li><li>必要なアクション (該当する場合) を実行し、アプリケーションをテストします。</li><li>ブレーク/修正シナリオが発生した場合は、サポート要求を作成します。</li></ul></td></tr><tr><td>変更後</td><td><ul><li>今後の変更のロールアウトを改善するために、顧客からのフィードバックを収集します。</li><li>データ信号を監視し、影響を受け取るキューをサポートします。</li></ul></td><td><ul><li>組織内のユーザーと一緒に作業し、変更を採用します。</li><li>変更管理プロセスと導入管理プロセスを確認して、効率を高める機会を得る。</li><li>管理者フィードバック ツールで、一般的なフィードバックと特定のフィードバックを提供します。</li><li>ユーザーがアプリ固有のフィードバックを提供するには、Windows フィードバック Hubアプリの [スマイル] ボタンOfficeします。</li></ul></td></tr>
<table> 

### <a name="change-types"></a>変更の種類

サービスに対して定期的に行う変更には、いくつかの種類があります。 これらの変更の通信チャネルと、ユーザーが担当するアクションは異なります。

すべての変更が、ユーザーに同じ影響を与えたり、同じアクションを必要としたりするわけではありません。 一部は計画済みで、計画されていないものがあります (セキュリティ以外の更新プログラムやセキュリティ更新プログラムは通常は計画されません)。 変更の種類によっては、通信チャネルが異なる場合があります。 次の表に、Microsoft Managed Desktop サービスで期待できる変更の種類を示します。

|   | 機能 | セキュリティ以外の更新プログラム | セキュリティ
--- | --- | --- | ---
**変更の種類** | - 機能の更新<br>- 新機能またはアプリケーション<br>- 非推奨の機能 | 問題に関するクライアント修正プログラム | セキュリティ更新プログラム
**事前通知** | アクションが必要な変更に関する 5 日間の通知 | いいえ、このような変更は月次リリースに含まれています | いいえ、月次リリースに変更が含まれています 
**通信チャネル** | - メッセージ センター<br>- 電子メール通知 | - メッセージ センター<br>- 電子メール通知 | - メッセージ センター<br>- 電子メール通知
**グローバル管理者の操作が必要** | 時々 | まれに | まれに 
**アクションの種類** | 設定の変更 | ユーザーへの変更の伝達 | 管理設定の変更  
**テストが必要** | リモート アクセス サービスを含むビジネス アプリケーションを確認する | 時々 - プロセスまたはカスタマイズに対する修正プログラムのテスト | まれに 
**変更の例** | - 機能更新プログラム: IT 管理者ポータルによるサポート チケットの提出とレビューの簡略化<br>- 新機能またはアプリケーション: Semi-Annual機能更新プログラムWindows 10リリース | お客様によって報告されたバグに基づく修正プログラム |

## <a name="standard-operating-procedures"></a>標準的な操作手順

Microsoft Managed Desktop サービスは、Microsoft クラウド インスタンスで Microsoft によって実装および運用され、他の管理アクティビティを行う可能性があります。 Microsoft は、Microsoft Managed Desktop 固有のセットアップ、構成、および操作の責任を負います。

オンプレミス製品の場合、組織はセットアップ、および構成と運用のアクティビティを管理する責任を負います。

Categories | Microsoft は、 | お客様は、
--- | --- | ---
ネットワーク (プロキシ、パケット 検査、VPN)  | ビジネス ユーザーに対するリスクを最小限に抑えるために、お客様にアドバイスを提供し、計画します。 | - Microsoft が確認する構成の詳細、スコープ、タイムライン、その他の関連する詳細など、計画された構成変更に関する情報を要求するサポート要求を作成します。<br>- 変更を適用できるのは、Microsoft Managed Desktop Operations が評価およびアドバイスを受け取った後のみです。
サービス アカウント |- 資格情報を実装、安全に保存、管理します。<br> - これらの資格情報の不正なアクセスまたは使用をセキュリティ運用チームに伝えます。 | - Microsoft が確認する構成の詳細、スコープ、タイムライン、その他の関連する詳細など、計画された構成変更に関する情報を要求するサポート要求を作成します。<br>- 変更を適用できるのは、Microsoft Managed Desktop Operations が評価およびアドバイスを受け取った後のみです。<br>- ポリシー、多要素認証、条件付きアクセス、またはアプリケーションの展開を Microsoft Managed Desktop Service アカウントに割り当てない。<br>- パスワードをリセットしないか、資格情報を使用しない。<br>- これらのサービス アカウントに関連する Intune または Azure 監査ログで疑わしいアクティビティが観察された場合は、Microsoft Managed Desktop Operations に対する Sev C サポート要求を開きます。
デバイス グループ | - Microsoft Managed Desktop グループ内のデバイスのメンバーシップを実装して割り当てる。<br>- Microsoft Managed Desktop グループを使用して、デバイスへの構成と更新プログラムの割り当てとリリースを管理します。 | - Microsoft が確認する構成の詳細、スコープ、タイムライン、その他の関連する詳細など、計画された構成変更に関する情報を要求するサポート要求を作成します。<br>- 変更を適用できるのは、Microsoft Managed Desktop Operations が評価およびアドバイスを受け取った後のみです。<br>- 「デバイスを展開グループに割り当てる」で説明されている手順に従って、Microsoft Managed Desktop グループにのみデバイス [を割り当てる](../working-with-managed-desktop/assign-deployment-group.md)。<br>- グループを使用して、VPN、ビジネスまたは電子メールの暗号化Windows Hello、企業の Wifi プロファイル構成などのサービスに企業証明書を割り当てる必要があります。<br>- 共同管理が存在する場合は、Configuration Manager クライアントを展開するときに、すべての Microsoft 管理デスクトップ グループを明示的に除外します。
ポリシー | - サービス内のデバイスの構成状態を管理する Microsoft Managed Desktop ポリシーを実装および管理します。<br>- デバイス グループを使用して、ポリシーまたはWindowsに更新プログラムを展開します。<br> - Microsoft 管理デスクトップ 以外のグループを対象として明示的に除外します。 | - Microsoft が確認する構成の詳細、スコープ、タイムライン、その他の関連する詳細など、計画された構成変更に関する情報を要求するサポート要求を作成します。<br>- 変更を適用できるのは、Microsoft Managed Desktop Operations が評価およびアドバイスを受け取った後のみです。<br>- Microsoft Managed Desktop サービスによって管理されていないデバイスまたはユーザーに、Microsoft Managed Desktop ポリシーを編集または割り当てない。
Microsoft Defender for Endpoint | Microsoft Managed Desktop サービスのスコープ内のデバイスを監視および調査します。 | - Microsoft が確認する構成の詳細、スコープ、タイムライン、その他の関連する詳細など、計画された構成変更に関する情報を要求するサポート要求を作成します。<br>- Microsoft Managed Desktop Operations が評価およびアドバイスを行った後にのみ変更を適用する
ビジネス向け Microsoft Store | Microsoft Managed Desktop サービスWindowsプロファイルを構成および管理します。 | - Microsoft が確認する構成の詳細、スコープ、タイムライン、その他の関連する詳細など、計画された構成変更に関する情報を要求するサポート要求を作成します。<br>- 変更を適用できるのは、Microsoft Managed Desktop Operations が評価およびアドバイスを受け取った後のみです。<br>- Microsoft Managed Desktop プロファイルの構成を変更しないWindows割り当てられたデバイスを追加または削除します。
証明書 | | - Microsoft が確認する構成の詳細、スコープ、タイムライン、その他の関連する詳細を含む、計画された構成変更に関する情報を要求する、証明書の有効期限が切れてから 60 日前にサポート 要求を作成します。<br>- 変更を適用できるのは、Microsoft Managed Desktop Operations が評価およびアドバイスを受け取った後のみです。<br>- 証明書プロファイル、VPN プロファイル、および証明書プロファイルを構成するために必要なすべての証明書Wi-Fiします。

## <a name="device-wipe-with-factory-reset"></a>工場出荷時の状態にリセットされたデバイスワイプ

Microsoft Managed Desktop Operations チームは、必要に応じて、サービスに登録されているデバイスの出荷時のリセットを実行できます。 リセットは、別の従業員にデバイスを提供する必要がある場合、または従業員が会社を離れる場合に役立ちます。

いくつかの要件があります。

- グローバル管理者は、サービス要求を送信する必要があります。
- 要求にデバイスのコンピューター名を含める。
- デバイスをリセットする前にAzure ADアカウントがインストールされている必要があります。

管理デスクトップ操作チームは、次の操作を実行します。

- Intune でデバイス名を検索する
- 出荷時のリセット コマンドをデバイスに送信する

> [!NOTE]
> デバイスがリセットされる前に、Azure ADアカウントを削除しない。 ユーザーがデバイスにAzure AD場合、Intune は出荷時のリセット コマンドをデバイスに送信できません。

デバイスは"箱から出たエクスペリエンス" で起動し、プレインストールされているアプリケーションと設定はすべて再び適用されます。 デバイスのユーザーは、初期セットアップ情報を再度提供する必要があります。 

デバイスがリセットされた場合は、組織内の別のユーザーにデバイスを提供できます。 前のユーザーのデータまたはエンタープライズ データはいずれもデバイス上に存在しない。 次のユーザーは、前のユーザーが新しい Microsoft マネージ デスクトップ デバイスで行ったのと同じプロセスを実行します。

BitLocker は、このプロセスのデータ セキュリティの重要なコンポーネントです。 Microsoft Managed Desktop デバイスでの BitLocker 暗号化では、デバイスが工場出荷時の状態にリセットされた後でも、ドライブ上のデータは安全に維持されます。 ドライブ上に保存されたデータは、デバイスの次のユーザーが使用できません。 詳細については [、「BitLocker の概要」を参照してください](/windows/security/information-protection/bitlocker/bitlocker-overview)。

詳細については、「デバイスを出荷 [時にリセットする」を参照してください](/intune/remote-actions/devices-wipe#factory-reset-a-device)。
