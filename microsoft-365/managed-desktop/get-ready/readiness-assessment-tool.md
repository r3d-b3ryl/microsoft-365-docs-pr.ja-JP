---
title: 準備状況評価ツール
description: ツールが実行されているかどうかと、結果の意味について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 56d849a7abcbe480d82200cc7841d42e9c189762
ms.sourcegitcommit: fa26da0be667d4be0121c52b05488dc76c5d626c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "48795107"
---
# <a name="readiness-assessment-tool"></a>準備状況評価ツール

Microsoft マネージドデスクトップに登録するときに、よりスムーズに実行できるようにするには、事前に設定しなければならない設定やその他のパラメーターがいくつかあります。 このツールを使用すると、これらの設定を確認して、適切でないものを修正するための詳細な手順を得ることができます。

このツールは、microsoft のマネージドデスクトップで機能することを確認するために、Microsoft エンドポイントマネージャー (特に、Microsoft Intune)、Azure Active Directory (Azure AD)、および Microsoft 365 の設定をチェックします。 Microsoft マネージドデスクトップは、前回 Azure AD 組織 (テナント) でチェックを実行してから12か月間、これらのチェックに関連付けられているデータを保持します。 12か月を過ぎると、そのフォームは重複して識別された形式で保持されます。  収集するデータを削除することもできます。

少なくとも Intune 管理者の役割を持つすべてのユーザーはこのツールを実行できますが、3つのチェック ([証明書コネクタ](readiness-assessment-fix.md#certificate-connectors)、 [多要素認証](readiness-assessment-fix.md#multi-factor-authentication)、および [セルフサービスのパスワードリセット](readiness-assessment-fix.md#self-service-password-reset)) には追加のアクセス許可が必要です。
 
評価ツールは、次の項目をチェックします。

## <a name="microsoft-intune-settings"></a>Microsoft Intune の設定

|小切手  |説明  |
|---------|---------|
|自動操縦展開プロファイル     | 自動操縦展開プロファイルの割り当てがすべてのデバイスに適用されないことを確認します (プロファイルを Microsoft マネージドデスクトップデバイスに割り当てることはでき *ません* )。       |
|証明書コネクタ     | 証明書コネクタの状態がアクティブであることを確認します。   |
|条件付きアクセス     | 条件付きアクセスポリシーがすべてのユーザーに割り当てられていないことを確認します (条件付きアクセスポリシーを Microsoft Managed Desktop サービスアカウントに割り当てることはでき *ません* )。    |
|デバイスコンプライアンスポリシー     | Intune コンプライアンスポリシーがすべてのユーザーに割り当てられていないことを確認します (ポリシーは、Microsoft マネージドデスクトップデバイスに割り当てられ *ない* ようにする必要があります)。    |
|デバイス構成プロファイル     | 構成プロファイルがすべてのユーザーまたはすべてのデバイスに割り当てられていないことを確認します (構成プロファイルを Microsoft マネージドデスクトップデバイスに割り当てることはでき *ません* )。     |
|デバイスの種類の制限     | 組織内の Windows 10 デバイスが Intune に登録することを許可されているかどうかを確認します。        |
|登録の状態ページ     | 登録の状態ページが有効になっていないことを確認する      |
|Intune の登録     | Azure AD 組織の Windows 10 デバイスが Intune に自動的に登録されていることを確認します。         |
|ビジネス向け Microsoft Store     | Microsoft Store for Business が有効になっており、Intune と同期されていることを確認します。        |
|多要素認証 | Microsoft マネージドデスクトップサービスアカウントに多要素認証が適用されていないことを確認します。
|PowerShell スクリプト     | Microsoft マネージドデスクトップデバイスを対象とする方法で Windows PowerShell スクリプトが割り当てられて *いない* ことを確認します。    |
|地域     | Microsoft マネージドデスクトップで地域がサポートされていることを確認する        |
|セキュリティベースライン     | セキュリティベースラインプロファイルがすべてのユーザーまたはすべてのデバイスを対象としていないことを確認します (セキュリティ基準ポリシーでは、Microsoft マネージドデスクトップデバイスを対象としてはいけ *ません* )。       |
|Windows アプリ     | Microsoft マネージドデスクトップデバイスに割り当てるアプリを確認する      |
|Windows Hello for Business     | Windows Hello for Business が有効になっていることを確認する        |
|Windows 10 の更新リング     | Intune の "Windows 10 update ring" ポリシーがすべてのユーザーまたはすべてのデバイスを対象としていないことを確認します (ポリシーは、Microsoft マネージデスクトップデバイスを対象とし *ていません* )。     |


## <a name="azure-active-directory-settings"></a>Azure Active Directory の設定

|小切手  |説明  |
|---------|---------|
|エンタープライズ状態ローミングの "アドホック" サブスクリプション     | 設定をチェックする方法 ("false" に設定されている場合) を確認する方法を説明します。エンタープライズ状態の移動が正常に動作しない可能性があります  |
|Enterprise State Roaming     | エンタープライズ状態ローミングが有効になっているかどうかを確認する方法をアドバイスします。       |
|ライセンス     | 必要な[ライセンス](prerequisites.md#more-about-licenses)を取得済みであることを確認します。         |
|多要素認証     | 多要素認証がすべてのユーザーに適用されていないことを確認します (多要素認証を誤って Microsoft Managed Desktop サービスアカウントに適用する必要はありません)。|
|セキュリティアカウント名   | Microsoft Managed Desktop が独自に使用するものと競合しているユーザー名がないことを確認します。        |
|セキュリティ管理者の役割     | セキュリティリーダ、セキュリティオペレーター、またはグローバル閲覧者の役割を持つユーザーに、エンドポイントの Microsoft Defender でこれらの役割が割り当てられていることを確認します。         |
|セキュリティの既定値 | Azure AD 組織のセキュリティの既定が Azure Active Directory で有効になっているかどうかを確認します。 |
|セルフサービスによるパスワードのリセット     | セルフサービスのパスワードのリセットが有効になっていることを確認する        |
|標準ユーザーの役割     | ユーザーが標準ユーザーであり、ローカル管理者権限を持っていないことを確認します。         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>エンタープライズ設定のための Microsoft 365 アプリ

|小切手  |説明  |
|---------|---------|
|OneDrive for Business     | OneDrive for Business がサポートされない設定を使用しているかどうかを確認します。        |


チェックが行われるたびに、ツールは次の4つの結果のいずれかを報告します。


|結果  |意味  |
|---------|---------|
|準備完了     | 登録を完了する前に、何もする必要はありません。        |
|アドバイザリ    | 登録とユーザーのための最適な手順については、このツールの手順を実行してください。 登録は完了 *でき* ますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。        |
|使用不可能 | これらの問題を修正しない場合、 *登録は失敗* します。 ツールの手順に従って解決します。        |
|Error | 使用している Azure Active Director (AD) の役割には、このチェックを実行するための十分な権限がありません。 |
