---
title: リテンション期間に使用できる PowerShell コマンドレットを特定する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: normal
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-compliance
description: 大規模な構成、自動化、または高度な構成シナリオに必要になる可能性があるリテンション期間用の PowerShell コマンドレットを特定します。
ms.openlocfilehash: 23dda0c7e5cdc2ce52c2dfca8e5ab575d5653b99
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66625987"
---
# <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベルの PowerShell コマンドレット

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

次のセクションを使用して、大規模な構成、自動化されたスクリプト、または高度な構成シナリオに必要なアイテム保持ポリシーと保持ラベルに使用できる主な PowerShell コマンドレットを特定します。 コマンドレットの完全な一覧については、PowerShell ドキュメントの [ポリシーとコンプライアンスの保持リスト](/powershell/module/exchange#policy-and-compliance-retention) を参照してください。

これらのコマンドレットを使用する前に、まず [Security & Compliance Center PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell)必要があります。

次の説明では、アイテム保持ポリシーはアイテム保持ポリシー (ラベルなし) またはアイテム保持ラベル ポリシーを参照できます。 各ポリシーは、それが静的かアダプティブかを定義し、ポリシーを適用する場所を定義します。 その後、ポリシーでは、構成を完了するために 1 つのルールが必要です。

例:
- アイテム保持ポリシーには、5 年間保持してから削除するなど、保持設定を定義するルールが必要です。

保持ラベルを使用する場合、これらのアイテムには保持設定が含まれており、それらのポリシーには異なるルールが必要です。
- 公開するアイテム保持ラベル ポリシーには、アプリに表示するラベルを定義するルールが必要です。
- アイテム保持ラベルの自動適用ポリシーには、適用するラベルとラベルを適用するための条件を定義するルールが必要です。

## <a name="retention-cmdlets-for-most-locations"></a>ほとんどの場所の保持コマンドレット

**Exchange メール**、**SharePoint サイト**、**OneDrive アカウント**、**Microsoft 365 グループ、Skype for Business****、****Exchange パブリック フォルダー**、**Teams チャット メッセージ**、Teams **チャネル メッセージ** の場合は、次の表のコマンドレットを使用します。

場所が Teams プライベート チャネル メッセージ、Yammer ユーザー メッセージ、または Yammer コミュニティ メッセージの場合は、これらのコマンドレットを使用しないでください。 これらの場所には、 [次のセクション](#retention-cmdlets-specific-to-teams-private-channels-and-yammer)で識別される代替コマンドレットがあります。

|コマンドレット|説明|該当する場所|
|:-----|:-----|:-----|:-----|
|[Enable-ComplianceTagStorage](/powershell/module/exchange/enable-compliancetagstorage) <br /><br /> [Get-ComplianceTagStorage](/powershell/module/exchange/enable-compliancetagstorage) |ストレージを作成するか、保持ラベルのそのストレージを表示する 1 回限りの操作 |Exchange メール <br /><br />SharePoint サイト <br /><br /> OneDrive アカウント <br /><br /> Microsoft 365 グループ|
|[Get-ComplianceTag](/powershell/module/exchange/get-compliancetag)<br /><br> [New-ComplianceTag](/powershell/module/exchange/new-compliancetag) <br /><br> [Remove-ComplianceTag](/powershell/module/exchange/remove-compliancetag) <br /><br> [Set-ComplianceTag](/powershell/module/exchange/set-compliancetag) |保持ラベルの表示、作成、削除、構成 |Exchange メール <br /><br /> SharePoint サイト <br /><br /> OneDrive アカウント<br /><br /> Microsoft 365 グループ|
|[Get-RecordReviewNotificationTemplateConfig](/powershell/module/exchange/get-recordreviewnotificationtemplateconfig) <br /><br /> [Set-RecordReviewNotificationTemplateConfig](/powershell/module/exchange/remove-retentioncompliancepolicy)  |廃棄レビュー通知とアラーム設定の構成を表示または構成する |Exchange メール <br /><br /> SharePoint サイト <br /><br /> OneDrive アカウント <br /><br /> Microsoft 365 グループ|
|[Get-RetentionCompliancePolicy](/powershell/module/exchange/get-retentioncompliancepolicy) <br /><br /> [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) <br /><br /> [Remove-RetentionCompliancePolicy](/powershell/module/exchange/remove-retentioncompliancepolicy) <br /><br /> [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) |保持用のポリシーの表示、作成、削除、構成 |Exchange メール <br /><br /> SharePoint サイト <br /><br /> OneDrive アカウント<br /><br /> Microsoft 365 グループ <br /><br /> Skype for Business <br /><br /> Exchange パブリック フォルダー <br /><br /> Teams のチャット メッセージ <br /><br /> チームのチャネル メッセージ |
|[Get-RetentionComplianceRule](/powershell/module/exchange/get-retentioncompliancepolicy) <br /><br /> [New-RetentionComplianceRule](/powershell/module/exchange/get-retentioncompliancepolicy) <br /><br /> [Set-RetentionComplianceRule](/powershell/module/exchange/set-retentioncompliancerule) <br /><br /> [Remove-RetentionComplianceRule](/powershell/module/exchange/remove-retentioncompliancerule)  | 保持ラベルまたは保持ラベルのポリシーの設定を表示、作成、構成、削除する |Exchange メール <br /><br /> SharePoint サイト <br /><br /> OneDrive アカウント <br /><br /> Microsoft 365 グループ <br /><br /> Skype for Business <br /><br /> Exchange パブリック フォルダー <br /><br /> Teams のチャット メッセージ <br /><br /> チームのチャネル メッセージ |

## <a name="retention-cmdlets-specific-to-teams-private-channels-and-yammer"></a>Teams プライベート チャネルと Yammer に固有の保持コマンドレット

**場所が Teams プライベート チャネル メッセージ**、**Yammer ユーザー** メッセージ、または **Yammer コミュニティ** メッセージの場合は、次のコマンドレットを使用します。

場所が Teams チャット メッセージ、Teams チャネル メッセージ、Exchange 電子メール、SharePoint サイト、OneDrive アカウント、Microsoft 365 グループ、Skype for Business、または Exchange パブリック フォルダーの場合は、[前のセクション](#retention-cmdlets-for-most-locations)に示したコマンドレットを使用します。

|コマンドレット|説明|該当する場所|
|:-----|:-----|:-----|:-----|
|[Get-AppRetentionCompliancePolicy](/powershell/module/exchange/get-appretentioncompliancepolicy) <br /><br> [New-AppRetentionCompliancePolicy](/powershell/module/exchange/new-appretentioncompliancepolicy) <br /><br> [Remove-AppRetentionCompliancePolicy](/powershell/module/exchange/remove-appretentioncompliancepolicy) <br /><br> [Set-AppRetentionCompliancePolicy](/powershell/module/exchange/remove-appretentioncompliancepolicy) | アイテム保持ポリシーの表示、作成、削除、構成 |Teams の非公開チャネル メッセージ <br /><br /> Yammer ユーザーのメッセージ <br /><br /> Yammer コミュニティのメッセージ|
|[Get-AppRetentionComplianceRule](/powershell/module/exchange/get-appretentioncompliancerule) <br /><br /> [New-AppRetentionComplianceRule](/powershell/module/exchange/new-appretentioncompliancerule) <br /><br /> [Remove-AppRetentionComplianceRule](/powershell/module/exchange/remove-appretentioncompliancerule) <br /><br /> [Set-AppRetentionComplianceRule](/powershell/module/exchange/remove-appretentioncompliancerule) | アイテム保持ポリシーの保持設定の表示、作成、削除、構成 |Teams の非公開チャネル メッセージ <br /><br /> Yammer ユーザーのメッセージ <br /><br /> Yammer コミュニティのメッセージ|

## <a name="configuration-guidance"></a>構成ガイダンス

詳細な情報と例については、各コマンドレットに関連付けられているヘルプ ページを使用してください。

保持ラベルの作成と発行に関するガイド付きヘルプについては、「 [PowerShell を使用した保持ラベルの作成と発行](bulk-create-publish-labels-using-powershell.md)」を参照してください。