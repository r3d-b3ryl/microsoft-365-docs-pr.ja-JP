---
title: アクション センターに移動して、自動化された調査および修復タスクを表示および承認する
description: アクション センターを使用して、自動化された調査の詳細を表示し、保留中のアクションを承認する
keywords: アクション センター、脅威の防止、調査、アラート、保留、自動化、検出
search.appverid: met150
ms.prod: M365-security-compliance
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 950dec4c0b0a2de2bdc60a73a12f6c7895189ea4
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911385"
---
# <a name="go-to-the-action-center-to-view-remediation-actions"></a>アクション センターに移動して修復アクションを表示する

**適用対象:**
- Microsoft Threat Protection

[!include[Prerelease information](prerelease.md)]

## <a name="a-single-pane-of-glass-experience"></a>「単一画面」エクスペリエンス

![アクション センター](../images/air-actioncenter.png)

アクション センターを使用して、組織のデバイスおよびメールボックス全体の現在および過去の調査結果を確認します。 脅威の種類および[出された判定](mtp-autoir-results.md#remediation-actions-following-automated-investigation)に応じて、修復アクションが自動的に、または組織のセキュリティ運用チームの承認を受けて実行されます。 すべての修復アクションは、承認待ちか既に承認済みかにかかわらず、アクションセンターに統合されます。 

アクション センターは、次のようなタスクに「単一画面」エクスペリエンスを提供します。
- 保留中の修復アクションを承認する。
- 承認済みの修復アクションの監査ログを表示する。
- 完了した修復アクションを確認する。

アクション センターは、職場で Microsoft Threat Protection の包括的なビューを提供するため、セキュリティ運用チームはより効果的かつ効率的に運用できます。

## <a name="remediation-actions"></a>修復アクション

次の表に、現在アクション センターでサポートされている修復アクションを示します。 

|エンドポイントの修復アクション  |メールの修復アクション  |
|---------|---------|
|ファイルの検疫<br/>レジストリ キーの削除<br/>プロセスの強制終了 <br/>サービスの停止 <br/>レジストリ キーの削除 <br/>ドライバーの無効化 <br/>スケジュールされたタスクの実行      |メール メッセージまたはクラスターの論理的な削除<br/>URL のブロック (クリック時)<br/>外部メール転送の無効化          |

## <a name="go-to-the-action-center"></a>アクション センターに移動する

1. [https://security.microsoft.com](https://security.microsoft.com) に移動し、サインインします。 

2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。 

3. [アクション センター] には、[**保留中**] と [**履歴**] の 2 つのタブが表示されます。

    - [**保留中**] タブには、続行するにはセキュリティ運用チームの誰かによる確認および承認が必要な調査のリストが表示されます。 ここに表示されている保留中のアイテムを確認し、実行してください。

    - [**履歴**] タブには、過去の調査や、自動的に実行された修復アクションのリストが表示されます。 過去 1 日、1 週間、1 か月、または 6 か月のデータを表示できます。

4. 表示する列のみを表示するには、[**列のカスタマイズ**] を選択します。<br/>![Microsoft Threat Protection のアクション センター](../images/mtp-action-center.png)

5. 調査の詳細を表示するには、リストから項目を選択します。 調査の詳細ビューが開きます。<br/>![調査の詳細](../images/mtp-air-investdetails.png)

    - 調査がメール コンテンツ (エンティティがメールボックスなど) に関連する場合は、調査の詳細は Office 365 セキュリティ/コンプライアンス センター に表示されます ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation))。 

    - 調査にデバイスが含まれる場合は、調査の詳細がセキュリティ センター で開きます ([https://security.microsoft.com](https://security.microsoft.com))。 

## <a name="required-permissions-for-action-center-tasks"></a>アクション センター タスクに必要なアクセス許可

アクション センターで保留中のアクションを承認または拒否するには、次の表に示すアクセス許可が割り当てられている必要があります。

|修復アクション |必要な役割と権限 |
|--|----|
|Microsoft Defender ATP の修復 (デバイス) |Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) または Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) で割り当てられた**セキュリティ管理者**の役割<br/>--- または ---<br/>Microsoft Defender ATP で割り当てられた**有効な修復アクション**の役割 <br/> <br/> 詳細については、次のリソースを参照してください。 <br/>- [Azure Active Directory での管理者役割のアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [役割ベースのアクセス制御のための役割の作成と管理 (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Office 365 ATP の修復 (Office コンテンツおよびメール)  |Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) または Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) で割り当てられた**セキュリティ管理者**の役割<br/>--- さらに --- <br/>Office 365 セキュリティ/コンプライアンス センターに割り当てられた**検索と消去**の役割 [https://protection.office.com](https://protection.office.com)) <br/><br/>**重要**: Office 365 セキュリティ/コンプライアンス センターにのみセキュリティ管理者の役割が割り当てられている場合は、アクション センターまたは Microsoft Threat Protection の機能にアクセスできません。 Azure Active Directory または Microsoft 365 管理センターでセキュリティ管理者の役割が割り当てられている必要があります。 <br/><br/>詳細については、次のリソースを参照してください。 <br/>- [Azure Active Directory での管理者役割のアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Office 365 セキュリティ/コンプライアンス センターのアクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Azure Active Directory で**グローバル管理者**の役割が割り当てられているユーザーは、アクション センターで保留中のアクションを承認または拒否できます。 ただし、ベスト プラクティスとして、グローバル管理者の役割が割り当てられているユーザーの数を制限する必要があります。 アクション センターのアクセス許可については、上記の**セキュリティ管理者**、**有効な修復アクション**、および**検索と消去**の役割を使用することをお勧めします。

## <a name="next-steps"></a>次のステップ 

- [Microsoft Threat Protection のインシデントの詳細](incidents-overview.md)
- [自動化された調査の結果を表示する](mtp-autoir-results.md)
- [Microsoft Threat Protection の捜索の詳細](advanced-hunting-overview.md)

