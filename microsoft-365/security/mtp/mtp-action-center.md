---
title: アクション センターに移動して、自動化された調査および修復タスクを表示および承認する
description: アクション センターを使用して、自動化された調査の詳細を表示し、保留中のアクションを承認する
keywords: アクション センター、脅威の防止、調査、アラート、保留、自動化、検出
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.openlocfilehash: aa9f433bc60949aa625d9346421b025121347a2c
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683321"
---
# <a name="the-action-center"></a>アクション センター

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

アクション センター ( ) を使用して、組織のデバイスとメールボックスに対する現在および過去の調査の結果 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) を確認します。 脅威の種類と結果の特定の状況に応じて、[](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions)修復アクションは自動的に行われるか、組織のセキュリティ運用チームの承認を受け取って行われます。 すべての修復アクションは、承認待ちか既に承認済みかにかかわらず、アクションセンターに統合されます。 

![アクション センター](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>「単一画面」エクスペリエンス

アクション センターは、次のようなタスクに「単一画面」エクスペリエンスを提供します。
- 保留中の修復アクションを承認する。
- 承認済みの修復アクションの監査ログを表示する。
- 完了した修復アクションを確認する。

アクション センターは、Microsoft 365 Defender の包括的なビューを動作中に提供しますので、セキュリティ運用チームは、より効果的かつ効率的に運用できます。

## <a name="go-to-the-action-center"></a>アクション センターに移動する

1. [https://security.microsoft.com](https://security.microsoft.com) に移動し、サインインします。 

2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。 

3. アクション センターには、[保留中] と [履歴] の **2 つのタブ****があります**。

    - [**保留中**] タブには、続行するにはセキュリティ運用チームの誰かによる確認および承認が必要な調査のリストが表示されます。 ここに表示されている保留中のアイテムを確認し、実行してください。

    - [**履歴**] タブには、過去の調査や、自動的に実行された修復アクションのリストが表示されます。 過去 1 日、1 週間、1 か月、または 6 か月のデータを表示できます。

4. 表示する列のみを表示するには、[**列のカスタマイズ**] を選択します。<br/>![Microsoft 365 Defender のアクション センター](../../media/mtp-action-center.png)

5. 調査の詳細を表示するには、リストから項目を選択します。 調査の詳細ビューが開きます。<br/>![調査の詳細](../../media/mtp-air-investdetails.png)

    - 調査が電子メールコンテンツ (エンティティがメールボックスなど) に関連する場合、セキュリティ/コンプライアンス センター () で調査&開きます [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) 。 

    - 調査にデバイスが含まれる場合は、調査の詳細がセキュリティ センター で開きます ([https://security.microsoft.com](https://security.microsoft.com))。 

> [!TIP]
> Microsoft 365 Defender の自動調査および対応機能によって何かが見逃された、または誤って検出されたと思う場合は、お知らせします。 [Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md)の自動調査および対応 (AIR) 機能で誤検知/陰性を報告する方法をご覧ください。

## <a name="available-actions"></a>使用可能なアクション

修復アクションを実行すると、アクション センターの [履歴] タブに一覧表示されます。 このようなアクションには、次のようなものがあります。

- 調査パッケージを収集する 
- デバイスを分離する (この操作は元に戻すことができます) 
- オフボード コンピューター 
- リリース コードの実行 
- 検疫からの解放 
- 要求サンプル 
- コードの実行を制限する (この操作は元に戻すことができます) 
- ウイルス対策スキャンを実行する 
- 停止と検疫 

> [!NOTE]
> セキュリティ運用チームは、自動的に実行される修復アクションに加えて、検出された脅威に対処するための手動アクションを実行できます。 自動修復アクションと手動修復アクションの詳細については、「修復アクション」 [を参照してください](mtp-remediation-actions.md)。

## <a name="action-source"></a>アクション ソース

(**NEW!**)ご存知のように、Microsoft 365 Defender は [、Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) や microsoft Defender for [Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)など、複数のサービス間で自動調査および対応機能を統合します。 新しい改善されたアクション センターには、各修復アクションの元の場所を示すアクション ソース列が追加されました。 

次の表に、可能なアクション ソース **の値を示** します。

| アクション ソースの値 | 説明 |
|:-----|:---|
| **デバイスの手動操作** | デバイスで手動で実行された操作。 たとえば、デバイスの[分離やファイル](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)[の検疫があります](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#stop-and-quarantine-files)。 |
| **手動の電子メール アクション** | 電子メールに対して手動で実行されるアクション。 たとえば、電子メール メッセージをソフト削除したり、電子 [メール メッセージを修復したりします](https://docs.microsoft.com/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365)。 |
| **自動デバイス アクション** | ファイルやプロセスなど、エンティティに対して自動的に実行されるアクション。 自動化されたアクションの例としては、検疫へのファイルの送信、プロセスの停止、レジストリ キーの削除があります。 (「Microsoft [Defender for Endpoint の修復アクション」をご覧ください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-auto-investigation#remediation-actions))。 |
| **自動電子メール アクション** | 電子メール メッセージ、添付ファイル、URL などの電子メール コンテンツに対して自動的に実行されるアクション。 自動化されたアクションの例としては、電子メール メッセージのソフト削除、URL のブロック、外部メール転送のオフがあります。 (Office [365 については、Microsoft Defender の修復アクションを参照](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)してください。 |
| **高度な検索アクション** | 高度な検索を使用してデバイスまたは電子 [メールで実行されるアクション](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview)。 |
| **エクスプローラーアクション** | エクスプローラーを使用してメール コンテンツに対して実行された [アクション](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)。 |
| **手動ライブ応答アクション** | ライブ応答を使用してデバイスで [実行されたアクション](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)。 たとえば、ファイルの削除、プロセスの停止、スケジュールされたタスクの削除などです。 |
| **ライブ応答アクション** | Microsoft Defender for [Endpoint API を使ってデバイスで実行されるアクション](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)。 アクションの例としては、デバイスの分離、ウイルス対策スキャンの実行、ファイルに関する情報の取得があります。 |

## <a name="required-permissions-for-action-center-tasks"></a>アクション センター タスクに必要なアクセス許可

アクション センターで保留中のアクションを承認または拒否するには、次の表に示すアクセス許可が割り当てられている必要があります。

|修復アクション |必要な役割と権限 |
|--|----|
|Microsoft Defender for Endpoint の修復 (デバイス) |Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) または Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) で割り当てられたセキュリティ管理者の役割<br/>--- または ---<br/>エンドポイント用 Microsoft Defender で割り当てられたアクティブな修復アクションの役割 <br/> <br/> 詳細については、次のリソースを参照してください。 <br/>- [Azure Active Directory での管理者役割のアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [役割ベースのアクセス制御の役割を作成および管理する (Microsoft Defender for Endpoint)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Microsoft Defender for Office 365 修復 (Officeコンテンツとメール)  |Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) または Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) で割り当てられたセキュリティ管理者の役割<br/>--- さらに --- <br/>セキュリティ センター コンプライアンス センター ( ) に割り&と削除の役割 [https://protection.office.com](https://protection.office.com) <br/><br/>**重要**: セキュリティ & コンプライアンス センターでのみセキュリティ管理者の役割が割り当てられている場合、アクション センターまたは Microsoft 365 Defender の機能にアクセスすることが可能ではありません。 Azure Active Directory または Microsoft 365 管理センターでセキュリティ管理者の役割が割り当てられている必要があります。 <br/><br/>詳細については、次のリソースを参照してください。 <br/>- [Azure Active Directory での管理者役割のアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [セキュリティ/コンプライアンス センター&アクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Azure Active Directory でグローバル管理者の役割が割り当てられているユーザーは、アクション センターで保留中のアクションを承認または拒否できます。 ただし、ベスト プラクティスとして、グローバル管理者の役割が割り当てられているユーザーの数を制限する必要があります。 アクション センターのアクセス許可については、上記のセキュリティ管理者、有効な修復アクション、および検索と消去の役割を使用することをお勧めします。

## <a name="next-steps"></a>次のステップ 

- [自動調査後に保留中のアクションを承認または拒否する](mtp-autoir-actions.md)
- [自動化された調査の結果を表示する](mtp-autoir-results.md)

