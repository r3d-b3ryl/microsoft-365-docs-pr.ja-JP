---
title: アクション センターに移動して、自動化された調査および修復タスクを表示および承認する
description: アクション センターを使用して、自動化された調査の詳細を表示し、保留中のアクションを承認する
keywords: アクション センター、脅威の防止、調査、アラート、保留、自動化、検出
search.appverid: met150
ms.prod: M365-security-compliance
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
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 77bc0f088a9779396a56a9cc8cc9ae6ecbdadea7
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503105"
---
# <a name="the-action-center"></a>アクション センター

**適用対象:**
- Microsoft Threat Protection

アクション センターを使用して、組織のデバイスおよびメールボックス全体の現在および過去の調査結果を確認します。 脅威の種類および結果の verdict に応じて、[修復アクション](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions)は自動的に、または組織のセキュリティ運用チームによる承認時に発生します。 すべての修復アクションは、承認待ちか既に承認済みかにかかわらず、アクションセンターに統合されます。 

![アクション センター](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>「単一画面」エクスペリエンス

アクション センターは、次のようなタスクに「単一画面」エクスペリエンスを提供します。
- 保留中の修復アクションを承認する。
- 承認済みの修復アクションの監査ログを表示する。
- 完了した修復アクションを確認する。

アクション センターは、職場で Microsoft Threat Protection の包括的なビューを提供するため、セキュリティ運用チームはより効果的かつ効率的に運用できます。

## <a name="go-to-the-action-center"></a>アクション センターに移動する

1. [https://security.microsoft.com](https://security.microsoft.com) に移動し、サインインします。 

2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。 

3. アクションセンターに、[**保留中**] と [**履歴**] という2つのタブが表示されます。

    - [**保留中**] タブには、続行するにはセキュリティ運用チームの誰かによる確認および承認が必要な調査のリストが表示されます。 ここに表示されている保留中のアイテムを確認し、実行してください。

    - [**履歴**] タブには、過去の調査や、自動的に実行された修復アクションのリストが表示されます。 過去 1 日、1 週間、1 か月、または 6 か月のデータを表示できます。

4. 表示する列のみを表示するには、[**列のカスタマイズ**] を選択します。<br/>![Microsoft Threat Protection のアクション センター](../../media/mtp-action-center.png)

5. 調査の詳細を表示するには、リストから項目を選択します。 調査の詳細ビューが開きます。<br/>![調査の詳細](../../media/mtp-air-investdetails.png)

    - 調査が電子メールコンテンツ (たとえば、エンティティがメールボックスなど) に関係している場合は、セキュリティ & コンプライアンスセンター () で調査の詳細を開き [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) ます。 

    - 調査にデバイスが含まれる場合は、調査の詳細がセキュリティ センター で開きます ([https://security.microsoft.com](https://security.microsoft.com))。 

> [!TIP]
> Microsoft の脅威保護の自動化された調査と応答機能によって何かが失敗したか、誤って検出されたと思われる場合は、お知らせください。 [Microsoft の脅威保護で自動調査と応答 (AIR) 機能の誤検知/ネガを報告する方法を](mtp-autoir-report-false-positives-negatives.md)参照してください。

## <a name="available-actions"></a>使用可能なアクション

修復アクションが実行されると、アクションセンターの [履歴] タブに一覧表示されます。 このような操作には、次のようなものがあります。

- 調査パッケージを収集する 
- デバイスを分離する (この操作は元に戻すことができます) 
- Offboard マシン 
- リリースコードの実行 
- 検疫からの解放 
- 要求のサンプル 
- コードの実行を制限する (この操作は元に戻すことができます) 
- ウイルス対策スキャンを実行する 
- 停止および検疫 

## <a name="required-permissions-for-action-center-tasks"></a>アクション センター タスクに必要なアクセス許可

アクション センターで保留中のアクションを承認または拒否するには、次の表に示すアクセス許可が割り当てられている必要があります。

|修復アクション |必要な役割と権限 |
|--|----|
|Microsoft Defender ATP の修復 (デバイス) |Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) または Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) で割り当てられたセキュリティ管理者の役割<br/>--- または ---<br/>Microsoft Defender ATP で割り当てられた有効な修復アクションの役割 <br/> <br/> 詳細については、次のリソースを参照してください。 <br/>- [Azure Active Directory での管理者役割のアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [役割ベースのアクセス制御のための役割の作成と管理 (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Office 365 ATP の修復 (Office コンテンツおよびメール)  |Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) または Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) で割り当てられたセキュリティ管理者の役割<br/>--- さらに --- <br/>セキュリティ & コンプライアンスセンター () に割り当てられた検索および削除の役割 [https://protection.office.com](https://protection.office.com) <br/><br/>**重要**: セキュリティ管理者の役割がセキュリティ & コンプライアンスセンターのみに割り当てられている場合は、アクションセンターまたは Microsoft の脅威保護機能にアクセスできません。 Azure Active Directory または Microsoft 365 管理センターでセキュリティ管理者の役割が割り当てられている必要があります。 <br/><br/>詳細については、次のリソースを参照してください。 <br/>- [Azure Active Directory での管理者役割のアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [セキュリティ & コンプライアンスセンターのアクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Azure Active Directory でグローバル管理者の役割が割り当てられているユーザーは、アクション センターで保留中のアクションを承認または拒否できます。 ただし、ベスト プラクティスとして、グローバル管理者の役割が割り当てられているユーザーの数を制限する必要があります。 アクション センターのアクセス許可については、上記のセキュリティ管理者、有効な修復アクション、および検索と消去の役割を使用することをお勧めします。

## <a name="next-steps"></a>次のステップ 

- [Microsoft Threat Protection のインシデントの詳細](incidents-overview.md)

- [自動化された調査の結果を表示する](mtp-autoir-results.md)

- [Microsoft Threat Protection の捜索の詳細](advanced-hunting-overview.md)

