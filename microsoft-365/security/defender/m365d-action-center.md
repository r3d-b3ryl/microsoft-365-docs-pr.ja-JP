---
title: アクション センターに移動して、自動化された調査および修復タスクを表示および承認する
description: アクション センターを使用して、自動調査に関する詳細を表示し、保留中のアクションを承認する
keywords: アクション センター, 脅威の保護, 調査, アラート, 保留中, 自動化, 検出
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
ms.date: 07/27/2022
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
ms.openlocfilehash: 9a44ea87a38228c5ec012f0fe507bb3c9d6f66bb
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67475484"
---
# <a name="the-action-center"></a>アクション センター

**適用対象:**
- Microsoft 365 Defender

アクション センターでは、次のようなインシデントタスクやアラート タスクに対して"1 つのガラスのウィンドウ" エクスペリエンスが提供されます。

- 保留中の修復アクションを承認する。
- 既に承認された修復アクションの監査ログを表示します。
- 完了した修復アクションを確認する。

アクション センターは、職場のMicrosoft 365 Defenderの包括的なビューを提供するため、セキュリティ運用チームは、より効果的かつ効率的に運用できます。

## <a name="the-unified-action-center"></a>統合アクション センター

統合アクション センター ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) には、デバイスの保留中と完了済みの修復アクション、電子メール &コラボレーション コンテンツ、ID が 1 つの場所に一覧表示されます。

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Microsoft 365 Defender ポータルの統合アクション センター。" lightbox="../../media/m3d-action-center-unified.png":::

以下に例を示します。 

- 以前に Office 365 セキュリティ & コンプライアンス センター ()[https://protection.office.com](https://protection.office.com) を使用していた場合は、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>で統合アクション センターを試してください。
- Microsoft Defender セキュリティ センター () でアクション センターを使用していた場合は、Microsoft 365 Defender[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">ポータル</a>で統合アクション センターを試します。
- <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>を既に使用している場合は、アクション センター ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) にいくつかの機能強化が表示されます。

統合アクション センターは、Defender for Endpoint とDefender for Office 365全体に修復アクションをまとめます。 すべての修復アクションに共通言語を定義し、統合された調査エクスペリエンスを提供します。 セキュリティ運用チームには、修復アクションを表示および管理するための "1 つのウィンドウ" エクスペリエンスがあります。  

適切なアクセス許可と次のサブスクリプションの 1 つ以上を持っている場合は、統合アクション センターを使用できます。

- [Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)
- [Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)
- [Microsoft 365 Defender](microsoft-365-defender.md)

> [!TIP]
> 詳細については、「 [要件](./prerequisites.md)」を参照してください。

承認待ちのアクションの一覧に移動するには、次の 2 つの方法があります。

- に移動するか、[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)
- Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) の [自動調査&応答] カード **で、[アクション センターで承認**] を選択します。

## <a name="using-the-action-center"></a>アクション センターの使用

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>に移動し、サインインします。 

2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。 または、[自動調査&応答] カード **で、[アクション センターで承認**] を選択します。

3. **[保留中のアクション]** タブと [**履歴]** タブを使用します。 次の表は、各タブに表示される内容をまとめたものです。

   |タブ  |説明  |
   |---------|---------|
   |**Pending**     | 注意が必要なアクションの一覧を表示します。 アクションを 1 つずつ承認または拒否したり、同じ種類のアクション (検疫ファイルなど) がある場合は複数のアクションを選択したりできます。 <br/><br/>自動調査を適時に完了できるように、保留中のアクションをできるだけ早く確認して承認 (または拒否) してください。       |
   |**履歴**     | 実行されたアクションの監査ログとして機能します。次のようになります。 <br/>- 自動調査の結果として実行された修復アクション <br/>- 疑わしい、または悪意のある電子メール メッセージ、ファイル、または URL に対して実行された修復アクション<br/>- セキュリティ運用チームによって承認された修復アクション <br/>- 実行されたコマンドと、ライブ応答セッション中に適用された修復アクション<br/>- ウイルス対策保護によって実行された修復アクション<br/><br/>特定のアクションを元に戻す方法を提供します ( [完了したアクションを元に戻すを](m365d-autoir-actions.md#undo-completed-actions)参照)。        |

4. アクション センターでは、データのカスタマイズ、並べ替え、フィルター処理、エクスポートを行うことができます。

   :::image type="content" source="../../media/m3d-action-center-columnsfilters.png" alt-text="アクション センターの並べ替え、フィルター処理、カスタマイズ機能を示すスクリーンショット。" lightbox="../../media/m3d-action-center-columnsfilters.png":::

   - 昇順または降順で項目を並べ替える列見出しを選択します。
   - 期間フィルターを使用して、過去の日、週、30 日間、または 6 か月間のデータを表示します。
   - 表示する列を選択します。
   - データの各ページに含める項目の数を指定します。
   - フィルターを使用して、表示するアイテムのみを表示します。
   - [ **エクスポート]** を選択して、結果を.csv ファイルにエクスポートします。

## <a name="actions-tracked-in-the-action-center"></a>アクション センターで追跡されるアクション

すべての修復アクションは、承認待ちか既に承認済みかにかかわらず、アクションセンターに統合されます。 使用可能なアクションは次のとおりです。

- 調査パッケージの収集 
- デバイスを分離する (この操作は元に戻すことができます) 
- コンピューターのオフロード 
- リリース コードの実行 
- 検疫からの解放 
- サンプルの要求 
- コードの実行を制限する (このアクションは元に戻すことができます) 
- ウイルス対策スキャンの実行 
- 停止と検疫 
- ネットワークからデバイスを格納する

アクション センターは、[自動調査](m365d-autoir.md)の結果として自動的に実行される修復アクションに加えて、検出された脅威に対処するためにセキュリティ チームが実行したアクションや、Microsoft 365 Defenderの脅威保護機能の結果として実行されたアクションも追跡します。 自動修復アクションと手動修復アクションの詳細については、「 [修復アクション」を](m365d-remediation-actions.md)参照してください。

## <a name="viewing-action-source-details"></a>アクション ソースの詳細の表示

(**NEW!**)改善されたアクション センターには、各アクションの送信元を示すアクション **ソース** 列が含まれるようになりました。 次の表では、 **使用可能なアクション ソース** の値について説明します。

| アクション ソースの値 | 説明 |
|:-----|:---|
| **手動デバイス アクション** | デバイスで実行される手動アクション。 たとえば、 [デバイスの分離](../defender-endpoint/respond-machine-alerts.md#isolate-devices-from-the-network) や [ファイルの検疫などがあります](../defender-endpoint/respond-file-alerts.md#stop-and-quarantine-files)。 |
| **手動の電子メール アクション** | 電子メールに対して実行される手動アクション。 たとえば、メール メッセージの論理的な削除や [電子メール メッセージの修復が含まれます](../office-365-security/remediate-malicious-email-delivered-office-365.md)。 |
| **自動デバイス アクション** | ファイルやプロセスなどのエンティティに対して実行される自動化されたアクション。 自動化されたアクションの例として、ファイルの検疫への送信、プロセスの停止、レジストリ キーの削除などがあります。 ([Microsoft Defender for Endpointの修復アクションを](../defender-endpoint/manage-auto-investigation.md#remediation-actions)参照してください)。 |
| **自動メール アクション** | 電子メール メッセージ、添付ファイル、URL など、電子メール コンテンツに対して実行される自動アクション。 自動化されたアクションの例には、メール メッセージの論理的な削除、URL のブロック、外部メール転送のオフなどがあります。 ([Microsoft Defender for Office 365の修復アクションを](../office-365-security/air-remediation-actions.md)参照してください)。 |
| **高度なハンティング アクション** | [高度なハンティング](./advanced-hunting-overview.md)を使用してデバイスまたは電子メールに対して実行されるアクション。 |
| **エクスプローラーアクション** | [エクスプローラー](../office-365-security/threat-explorer.md)で電子メール コンテンツに対して実行されるアクション。 |
| **手動のライブ応答アクション** | [ライブ応答](../defender-endpoint/live-response.md)を使用してデバイスで実行されたアクション。 たとえば、ファイルの削除、プロセスの停止、スケジュールされたタスクの削除などがあります。 |
| **ライブ応答アクション** | [Microsoft Defender for Endpoint API を](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)使用してデバイスで実行されたアクション。 アクションの例としては、デバイスの分離、ウイルス対策スキャンの実行、ファイルに関する情報の取得などがあります。 |

## <a name="required-permissions-for-action-center-tasks"></a>アクション センター タスクに必要なアクセス許可

アクション センターで保留中のアクションの承認や拒否などのタスクを実行するには、次の表に示すようにアクセス許可を割り当てる必要があります。

|修復アクション |必要な役割と権限 |
|--|----|
|Microsoft Defender for Endpoint修復 (デバイス) |Azure Active Directory (Azure AD) () または Microsoft 365 管理センター [https://admin.microsoft.com](https://admin.microsoft.com) ([https://portal.azure.com](https://portal.azure.com)) で割り当てられた **セキュリティ管理者** ロール<br/>--- または ---<br/>Microsoft Defender for Endpointで割り当てられた **アクティブな修復アクション** ロール <br/> <br/> 詳細については、次のリソースを参照してください。 <br/>- [Azure AD 組み込みロール](/azure/active-directory/roles/permissions-reference)<br/>- [ロールベースのアクセス制御のロールを作成および管理する (Microsoft Defender for Endpoint)](../defender-endpoint/user-roles.md)  |
|Microsoft Defender for Office 365修復 (Office コンテンツと電子メール)  |Azure AD () または Microsoft 365 管理センター [https://admin.microsoft.com](https://admin.microsoft.com) ([https://portal.azure.com](https://portal.azure.com)) で割り当てられた **セキュリティ管理者** ロール<br/>--- さらに --- <br/>セキュリティ & コンプライアンス センターで割り当てられた **検索ロールと消去** ロール ([https://protection.office.com](https://protection.office.com)) <br/><br/>**重要**: **Office 365 セキュリティ** & コンプライアンス センター ()[https://protection.office.com](https://protection.office.com) でのみセキュリティ管理者ロールが割り当てられている場合は、アクション センターまたはMicrosoft 365 Defender機能にアクセスできません。 Azure AD またはMicrosoft 365 管理センターで **セキュリティ管理者** ロールが割り当てられている必要があります。 <br/><br/>詳細については、次のリソースを参照してください。 <br/>- [Azure AD 組み込みロール](/azure/active-directory/roles/permissions-reference)<br/>- [セキュリティ & コンプライアンス センターのアクセス許可](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!TIP]
> Azure AD で **グローバル管理者** ロールが割り当てられているユーザーは、アクション センターで保留中のアクションを承認または拒否できます。 ただし、ベスト プラクティスとして、組織は **グローバル管理者** ロールが割り当てられているユーザーの数を制限する必要があります。 アクション センターのアクセス許可については、前の表に記載されている **セキュリティ管理者**、 **アクティブな修復アクション**、 **および検索と消去** のロールを使用することをお勧めします。

## <a name="next-step"></a>次のステップ 

- [修復アクションを表示および管理する](m365d-autoir-actions.md)
