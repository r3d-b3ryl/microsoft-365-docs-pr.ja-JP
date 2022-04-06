---
title: アクション センターに移動して、自動化された調査および修復タスクを表示および承認する
description: アクション センターを使用して、自動調査の詳細を表示し、保留中のアクションを承認する
keywords: アクション センター、脅威保護、調査、アラート、保留中、自動化、検出
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.openlocfilehash: e4ac7636b019b0e8c1d00487e95335ede4600d85
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64570043"
---
# <a name="the-action-center"></a>アクション センター

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

アクション センターは、次のようなインシデントタスクやアラート タスクに対して"単一ウィンドウ のガラス" エクスペリエンスを提供します。

- 保留中の修復アクションの承認。
- 既に承認されている修復アクションの監査ログを表示する。
- 完了した修復アクションを確認する。

アクション センターは、作業中のユーザーのMicrosoft 365 Defenderビューを提供しますので、セキュリティ運用チームは、より効果的かつ効率的に運用できます。

## <a name="the-unified-action-center"></a>統合アクション センター

統合アクション センター ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) には、デバイスの保留中および完了済み修復アクション、電子メール &コラボレーション コンテンツ、および ID が 1 つの場所に一覧表示されます。

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="ポータルの統合アクション センター Microsoft 365 Defenderします。" lightbox="../../media/m3d-action-center-unified.png":::

例: 

- コンプライアンス センター ([https://protection.office.com](https://protection.office.com)) で Office 365 セキュリティ &使用していた場合は、Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">ポータルで統合アクション センターをMicrosoft 365 Defenderしてください</a>。
- () のアクション センターを使用している場合は、[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)Microsoft Defender セキュリティ センターポータルで統合アクション センター<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">をMicrosoft 365 Defenderしてください</a>。
- このポータルを既に使用<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender、</a>アクション センター () にいくつかの機能強化が表示されます[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)。

統合アクション センターでは、Defender for Endpoint とエンドポイントの間で修復アクションDefender for Office 365。 すべての修復アクションの共通言語を定義し、統合された調査エクスペリエンスを提供します。 セキュリティ運用チームには、修復アクションを表示および管理するための"単一のガラス枠" エクスペリエンスがあります。  

適切なアクセス許可と次のサブスクリプションの 1 つ以上がある場合は、統合アクション センターを使用できます。

- [Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)
- [Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)
- [Microsoft 365 Defender](microsoft-365-defender.md)

> [!TIP]
> 詳細については、「要件」 [を参照してください](./prerequisites.md)。

## <a name="using-the-action-center"></a>アクション センターの使用

1. [ポータル] <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderに移動し</a>、サインインします。 
2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。 

アクション センターにアクセスすると、[保留中のアクション] と [履歴] **の 2 つのタブ** が **表示されます**。 次の表に、各タブに表示される内容の概要を示します。

|タブ  |説明  |
|---------|---------|
|**Pending**     | 注意が必要なアクションの一覧を表示します。 アクションを一度に 1 つ承認または拒否するか、同じ種類のアクション (検疫ファイルなど) がある場合は複数のアクションを選択できます。 <p>**ヒント**: 自動化された調査が、時間に合った方法で完了するように、保留中のアクションをできるだけ早く確認して承認 (または拒否) してください。       |
|**履歴**     | 次のようなアクションの監査ログとして機能します。 <br/>- 自動調査の結果として実行された修復アクション <br/>- 疑わしいまたは悪意のある電子メール メッセージ、ファイル、または URL に対して実行された修復アクション<br/>- セキュリティ運用チームによって承認された修復アクション <br/>- Live Response セッション中に適用された、実行されたコマンドと修復アクション<br/>- ウイルス対策保護によって実行された修復アクション <p>特定のアクションを元に戻す方法を提供します (「完了した操作を元に戻[す」を参照)。](m365d-autoir-actions.md#undo-completed-actions)        |

アクション センターでデータをカスタマイズ、並べ替え、フィルター処理、およびエクスポートできます。

:::image type="content" source="../../media/m3d-action-center-columnsfilters.png" alt-text="アクション センターの並べ替え、フィルター、およびカスタマイズ機能" lightbox="../../media/m3d-action-center-columnsfilters.png":::

- 列見出しを選択して、アイテムを昇順または降順に並べ替えます。
- 期間フィルターを使用して、過去の日、週、30 日、または 6 か月のデータを表示します。
- 表示する列を選択します。
- データの各ページに含めるアイテムの数を指定します。
- フィルターを使用して、表示するアイテムを表示します。
- [エクスポート **] を** 選択して、結果を.csvします。

## <a name="actions-tracked-in-the-action-center"></a>アクション センターで追跡されるアクション

すべての修復アクションは、承認待ちか既に承認済みかにかかわらず、アクションセンターに統合されます。 使用可能なアクションには、次のものが含まれます。

- 調査パッケージの収集 
- デバイスを分離する (この操作は元に戻すことができます) 
- コンピューターのオフロード 
- リリース コードの実行 
- 検疫からの解放 
- サンプルの要求 
- コードの実行を制限する (このアクションは元に戻すことができます) 
- ウイルス対策スキャンの実行 
- 停止と検疫 

自動調査の結果として自動的に実行される修復アクションに加[](m365d-autoir.md)えて、アクション センターは、検出された脅威に対処するためにセキュリティ チームが実行したアクションと、Microsoft 365 Defender の脅威保護機能の結果として実行されたアクションも追跡します。 自動修復アクションと手動修復アクションの詳細については、「修復アクション [」を参照してください](m365d-remediation-actions.md)。

## <a name="viewing-action-source-details"></a>アクション ソースの詳細の表示

(**NEW!**)改善されたアクション センターに、 **各アクションの** 送信元を示す [アクション ソース] 列が追加されました。 次の表に、可能な **アクション ソース値について説明** します。

| アクション ソースの値 | 説明 |
|:-----|:---|
| **デバイスの手動操作** | デバイスで手動で実行される操作。 たとえば、デバイスの[分離やファイル](../defender-endpoint/respond-machine-alerts.md#isolate-devices-from-the-network)[検疫が含まれます](../defender-endpoint/respond-file-alerts.md#stop-and-quarantine-files)。 |
| **手動の電子メール 操作** | 電子メールに対して手動で実行される操作。 たとえば、電子メール メッセージをソフト削除したり、 [電子メール メッセージを修復したりします](../office-365-security/remediate-malicious-email-delivered-office-365.md)。 |
| **デバイスの自動操作** | ファイルやプロセスなど、エンティティに対して実行される自動アクション。 自動操作の例としては、ファイルを検疫に送信する、プロセスを停止する、レジストリ キーを削除するなどの操作があります。 (「[修復アクション」を参照Microsoft Defender for Endpoint](../defender-endpoint/manage-auto-investigation.md#remediation-actions)。) |
| **電子メールの自動操作** | 電子メール メッセージ、添付ファイル、URL などの電子メール コンテンツに対して実行される自動アクション。 自動化されたアクションの例としては、電子メール メッセージのソフト削除、URL のブロック、外部メール転送のオフが含まれます。 (「[修復アクション」を参照Microsoft Defender for Office 365](../office-365-security/air-remediation-actions.md))。 |
| **高度なハンティング アクション** | 高度な検索を使用してデバイスまたは電子メールで [実行されるアクション](./advanced-hunting-overview.md)。 |
| **エクスプローラー アクション** | Explorer を使用して電子メール コンテンツに対して実行 [されるアクション](../office-365-security/threat-explorer.md)。 |
| **手動のライブ応答アクション** | ライブ応答を持つデバイスで [実行されるアクション](../defender-endpoint/live-response.md)。 たとえば、ファイルの削除、プロセスの停止、スケジュールされたタスクの削除が含まれます。 |
| **ライブ応答アクション** | API を使用してデバイス[で実行Microsoft Defender for Endpoint操作](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)。 アクションの例としては、デバイスの分離、ウイルス対策スキャンの実行、ファイルに関する情報の取得があります。 |

## <a name="required-permissions-for-action-center-tasks"></a>アクション センター タスクに必要なアクセス許可

アクション センターで保留中のアクションの承認や拒否などのタスクを実行するには、次の表に示すアクセス許可が割り当てられている必要があります。

|修復アクション |必要な役割と権限 |
|--|----|
|Microsoft Defender for Endpoint修復 (デバイス) |**セキュリティ管理者の** 役割は、Azure Active Directory (Azure AD) またはセキュリティ 管理者 ([https://portal.azure.com](https://portal.azure.com)) Microsoft 365 管理センター割 [https://admin.microsoft.com](https://admin.microsoft.com)り当てられます。<br/>--- または ---<br/>**ユーザーに割り当** てられたアクティブな修復アクションMicrosoft Defender for Endpoint <br/> <br/> 詳細については、次のリソースを参照してください。 <br/>- [Azure AD組み込みの役割](/azure/active-directory/roles/permissions-reference)<br/>- [役割ベースのアクセス制御の役割を作成および管理する (Microsoft Defender for Endpoint)](../defender-endpoint/user-roles.md)  |
|Microsoft Defender for Office 365修復 (Officeメール)  |**セキュリティ管理者の** 役割は、Azure AD ([https://portal.azure.com](https://portal.azure.com)) または Microsoft 365 管理センター () で割 [https://admin.microsoft.com](https://admin.microsoft.com)り当てられます。<br/>--- さらに --- <br/>**セキュリティ コンプライアンス センターで** 割り当てられた検索&削除の役割 ([https://protection.office.com](https://protection.office.com)) <br/><br/>**重要**: Office 365 セキュリティ & コンプライアンス  センター ([https://protection.office.com](https://protection.office.com)) でのみセキュリティ管理者の役割が割り当てられている場合は、アクション センターまたは Microsoft 365 Defender 機能にアクセスできます。 管理者または管理者に **セキュリティ管理者** の役割が割りAzure AD必要Microsoft 365 管理センター。 <br/><br/>詳細については、次のリソースを参照してください。 <br/>- [Azure AD組み込みの役割](/azure/active-directory/roles/permissions-reference)<br/>- [セキュリティ コンプライアンス センター&アクセス許可](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!TIP]
> グローバル管理者 **の役割が** 割り当てられているユーザー Azure ADアクション センターで保留中のアクションを承認または拒否できます。 ただし、ベスト プラクティスとして、組織はグローバル管理者の役割が割り当てられているユーザー **の数を制限する必要** があります。 アクション センターのアクセス許可 **については、** 前の表に記載されているセキュリティ管理者、アクティブな修復アクション、および検索と削除の役割を使用することをお勧めします。 

## <a name="next-step"></a>次の手順 

- [修復アクションを表示および管理する](m365d-autoir-actions.md)
