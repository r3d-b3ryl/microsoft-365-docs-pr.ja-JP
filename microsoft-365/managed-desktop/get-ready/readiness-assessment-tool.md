---
title: 準備状況評価ツール
description: 2 つのツール、実行するチェック、および結果の意味について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: caf9274284548a179e088131930ae832c098b521
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579400"
---
# <a name="readiness-assessment-tools"></a>準備状況評価ツール

Microsoft Managed Desktop に登録する際に、可能な限りスムーズなエクスペリエンスを実現するために、前もって設定する必要がある設定や他のパラメーター、および満たすために特定のデバイスおよびネットワーク要件があります。 Microsoft Managed Desktop Admin ポータルからアクセスされる 1 つのツールは、管理関連の設定をチェックします。 ダウンロード可能な別のツールは、個々のデバイス要件とネットワーク設定をチェックします。 これらのツールを使用して、これらの設定を確認し、適切でない設定を修正するための詳細な手順を受け取ってください。

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>デバイスとネットワークのダウンロード可能な準備状況評価チェッカー

ダウンロード可能な準備状況評価チェッカーの使用の詳細については、「ダウンロード可能な準備状況 [評価チェッカー」を参照してください](readiness-assessment-downloadable.md)。

## <a name="online-readiness-assessment-tool-for-management-settings"></a>管理設定のオンライン準備評価ツール

オンライン [ツールは](https://aka.ms/mmdart) 、Microsoft Endpoint Manager (具体的には Microsoft Intune)、Azure Active Directory (Azure AD)、Microsoft 365 の設定をチェックして、Microsoft マネージ デスクトップで動作するようにします。 Microsoft Managed Desktop は、Azure 管理組織 (テナント) で前回チェックを実行した後、これらのチェックに関連付けられたデータAD保持します。 12 か月後、識別されていない形式で保持されます。 収集したデータを削除できます。

少なくともグローバル リーダーまたは Intune 管理者の役割を持つユーザーは、このツールを実行できますが、2 つのチェック[](readiness-assessment-fix.md#multifactor-authentication)[(条件付](readiness-assessment-fix.md#conditional-access-policies)きアクセス ポリシーと多要素認証には追加のアクセス許可が必要です)。
 
評価ツールは、次の項目をチェックします。

## <a name="microsoft-intune-settings"></a>Microsoft Intune の設定

|小切手  |説明  |
|---------|---------|
|自動パイロット展開プロファイル     | Autopilot 展開プロファイルの割り当てがすべてのデバイスに適用されないか確認します (プロファイルを Microsoft 管理デスクトップ デバイスに割り当てる必要があります)。       |
|証明書コネクタ     | 証明書コネクタの状態をチェックして、アクティブな状態を確認します。   |
|条件付きアクセス     | 条件付きアクセス ポリシーがすべてのユーザーに割り当てられていないか確認します (条件付きアクセス ポリシーを Microsoft Managed Desktop サービス アカウントに割り当てる必要はありません)。    |
|デバイス コンプライアンス ポリシー     | Intune コンプライアンス ポリシーがすべてのユーザーに割り当てられていないか確認します(ポリシーを Microsoft 管理デスクトップ デバイスに割り当てる必要があります)。    |
|デバイス構成プロファイル     | 構成プロファイルがすべてのユーザーまたはすべてのデバイスに割り当てられていないか確認します (構成プロファイルを Microsoft 管理デスクトップ デバイスに割り当てる必要があります)。     |
|デバイスの種類の制限     | 組織内の Windows 10 デバイスで Intune への登録が許可されていないことを確認する        |
|[登録の状態] ページ     | [登録の状態] ページが有効になっていないか確認する      |
|Intune の登録     | Azure 組織の Windows 10 デバイスAD Intune に自動的に登録されるのを確認します。         |
|ビジネス向け Microsoft Store     | Microsoft Store for Business が有効で Intune と同期されているのを確認する        |
|多要素認証 | 多要素認証が Microsoft Managed Desktop サービス アカウントに適用されていないか確認します。
|PowerShell スクリプト     | Microsoft 管理Windows PowerShellデバイス *を* 対象とする方法で、スクリプトが割り当てられていないか確認する    |
|Region     | 地域が Microsoft Managed Desktop でサポートされているチェック        |
|セキュリティベースライン     | セキュリティ 基準プロファイルがすべてのユーザーまたはすべてのデバイスを対象としていないか確認します (セキュリティ基準ポリシーは、Microsoft 管理デスクトップ デバイスを対象とすべきではありません)。       |
|Windows アプリ     | Microsoft Managed Desktop デバイスに割り当てるアプリを確認する      |
|Windows Hello for Business     | Windows Hello for Business が有効になっているか確認する        |
|Windows 10 更新プログラム リング     | Intune の "Windows 10 更新リング" ポリシーがすべてのユーザーまたはすべてのデバイスを対象としていないか確認します (ポリシーは、Microsoft 管理デスクトップ デバイスを対象とすべきではありません)。     |


## <a name="azure-active-directory-settings"></a>Azure Active Directory の設定

|小切手  |説明  |
|---------|---------|
|エンタープライズ状態ローミングの "アドホック" サブスクリプション     | ("false" に設定されている場合) エンタープライズ状態ローミングが正しく動作しない可能性がある設定を確認する方法について説明します。  |
|Enterprise State Roaming     | エンタープライズ状態ローミングが有効になっているか確認する方法について説明します。       |
|ライセンス     | 必要なライセンスを [取得したチェック](prerequisites.md#more-about-licenses)         |
|多要素認証     | 多要素認証がすべてのユーザーに適用されないか確認します (多要素認証を Microsoft Managed Desktop サービス アカウントに誤って適用しなけり。|
|セキュリティ アカウント名   | Microsoft Managed Desktop が独自に使用するために予約したユーザー名と競合が発生しなか        |
|セキュリティ管理者の役割     | Microsoft Defender for Endpoint でセキュリティ リーダー、セキュリティ オペレーター、またはグローバル リーダーの役割を持つユーザーにそれらの役割が割り当てられているか確認します。         |
|セキュリティの既定値 | Azure Active Directory で Azure ADが有効になっているかどうかを確認します。 |
|セルフサービスによるパスワードのリセット     | セルフサービス パスワードのリセットが有効になっているか確認する        |
|標準ユーザー ロール     | ユーザーが標準ユーザーであり、ローカル管理者権限を持たなかっているのを確認します。         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Microsoft 365 Apps for enterprise settings

|小切手  |説明  |
|---------|---------|
|OneDrive for Business     | OneDrive for Business でサポートされていない設定が使用されているかどうかを確認します。        |


チェックごとに、ツールは次の 4 つの結果のいずれかを報告します。


|結果  |意味  |
|---------|---------|
|準備完了     | 登録を完了する前に、アクションは必要ありません。        |
|アドバイザリ    | 登録とユーザーの最適なエクスペリエンスを得るには、ツールの手順に従います。 登録 *は* 完了できますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。        |
|使用不可能 | *これらの問題を* 解決しない場合、登録は失敗します。 ツールの手順に従って解決します。        |
|Error | 使用している Azure Active Director (AD) ロールには、このチェックを実行するための十分なアクセス許可が付与されません。 |

## <a name="after-enrollment"></a>登録後

Microsoft Managed Desktop への登録が完了したら、Intune と Azure の特定の設定に戻って調整ADしてください。 詳細については、「登録後に [設定を調整する」を参照してください](../get-started/conditional-access.md)。

## <a name="steps-to-get-ready"></a>準備の手順

1. [Microsoft Managed Desktop の前提条件を確認します](prerequisites.md)。
2. 準備 [状況評価ツールを使用します](readiness-assessment-tool.md)。 (この記事)
3. [ゲスト アカウントの前提条件](guest-accounts.md)
4. [Microsoft マネージド デスクトップのネットワーク構成](network.md)
5. [Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する](certs-wifi-lan.md)
6. [Microsoft マネージド デスクトップ用にオンプレミス リソースアクセスを準備する](authentication.md)
7. [Microsoft マネージド デスクトップのアプリ](apps.md)
8. [Microsoft マネージド デスクトップ用に、マップされたドライブを準備する](mapped-drives.md)
9. [Microsoft マネージド デスクトップ用に、印刷リソースを準備する](printing.md)
