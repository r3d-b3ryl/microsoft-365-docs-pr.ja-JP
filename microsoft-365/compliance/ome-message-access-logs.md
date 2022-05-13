---
title: 暗号化されたメッセージ ポータル アクティビティ ログ
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.date: 05/12/2022
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: アクセス ログは、暗号化されたメッセージ ポータルから取得された暗号化されたメッセージに対して使用できます。
ms.openlocfilehash: 50656d1695d8fc3d6e81de6afc03b3f4e3c5ccee
ms.sourcegitcommit: 54bc063818779e351ca24f04ba571f762d85751d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2022
ms.locfileid: "65393226"
---
# <a name="encrypted-message-portal-activity-log-by-microsoft-purview-advanced-message-encryption-preview"></a>Microsoft Purview高度なメッセージ暗号化による暗号化されたメッセージ ポータルアクティビティ ログ (プレビュー)

アクセス ログは、暗号化されたメッセージ ポータルを介して暗号化されたメッセージに対して使用できます。これにより、組織は、メッセージがいつ読み取られ、外部の受信者によって転送されたかを判断できます。 外部受信者がログを使用できるようにするには、ポータル エクスペリエンスを適用する外部受信者に組織から送信された保護された電子メールにカスタム ブランド テンプレートを適用する必要があります。 「[暗号化されたメッセージに組織のブランドを追加する](add-your-organization-brand-to-encrypted-messages.md)」を参照してください。

## <a name="enabling-message-access-audit-logs-in-powershell"></a>PowerShell でメッセージ アクセス監査ログを有効にする

PowerShell を使用してアクセス ログExchange Online有効にすることができます。 Set-IrmConfigurationの *-EnablePortalTrackingLogs* パラメーターは、暗号化されたメッセージ ポータルにアクセスする監査ログを有効にするかどうかを指定します。 有効な値は次のとおりです。

- $true: 監査機能を有効にします。
- $false: 監査機能を無効にする

例: Set-IrmConfiguration -EnablePortalTrackingLogs $true

詳細については、「 [Set-IRMConfiguration (ExchangePowerShell)](/powershell/module/exchange/set-irmconfiguration)」を参照してください。

## <a name="message-access-audit-information"></a>メッセージ アクセス監査情報

アクセス ログには、次の種類のアクティビティについて、暗号化されたメッセージ ポータルから送信されたメッセージのエントリが含まれています。

- 外部ユーザー ログイン のタイムスタンプと認証方法
- 外部ユーザーがメッセージまたは添付ファイルを読み取る
- 添付ファイルのダウンロード
- メールの返信と転送

メッセージ アクセス ログ スキーマの詳細については、「 [コンプライアンス ポータルで監査ログを検索する」を参照してください](search-the-audit-log-in-security-and-compliance.md#encrypted-message-portal-activities)。

## <a name="search-for-events-in-the-message-access-logs"></a>メッセージ アクセス ログ内のイベントを検索する

メッセージ アクセス ログでキャプチャされたイベントを表示するには、

1. Microsoft Purview コンプライアンス ポータルの [**ソリューション**] で [監査] を選択 **します**。
1. [ **検索**] で、[ **アクティビティ** ] のドロップダウンをクリックし、暗号化されたメッセージ ポータル アクティビティを入力します。
1. 暗号化されたメッセージ ポータル アクティビティで、検索で使用するイベントの種類を選択します。 検索の日付範囲を設定します (既定値は前の週です)。必要に応じて、組織内の特定のユーザーを検索用に追加することもできます。 準備ができたら、[検索] を選択 **します**。
1. 監査プロパティを表示するには、一覧からイベントを選択します。
