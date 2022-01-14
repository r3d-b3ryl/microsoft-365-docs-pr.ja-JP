---
title: 準備状況の評価ツール
description: 2 つのツール、それらが実行するチェック、および結果の意味について説明します
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 866cebcf036c3b70470379139603a5addadb5b95
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035584"
---
# <a name="readiness-assessment-tools"></a>準備状況の評価ツール

Microsoft Managed Desktop に登録するときに可能な限りスムーズなエクスペリエンスを実現するには、事前に設定する必要のある設定やその他のパラメーター、および満たす必要のある特定のデバイスとネットワークの要件があります。 Microsoft Managed Desktop 管理者ポータルからアクセスする 1 つのツールは、管理関連の設定をチェックします。 ダウンロード可能な別のツールは、個々のデバイス要件とネットワーク設定をチェックします。 これらのツールを使用して、これらの設定を確認し、正しくないものを修正するための詳細な手順を受け取ることができます。

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>デバイスとネットワーク用のダウンロード可能な準備評価チェック

ダウンロード可能な準備評価チェックーの使用の詳細については、「[ダウンロード可能な準備評価チェック](readiness-assessment-downloadable.md)」を参照してください。

## <a name="online-readiness-assessment-tool-for-management-settings"></a>管理設定のためのオンライン準備評価ツール

[オンライン ツール](https://aka.ms/mmdart)は、Microsoft エンドポイント マネージャー (具体的には、Microsoft Intune)、Azure Active Directory (Azure AD)、およびMicrosoft 365 の設定をチェックして、Microsoft Managed Desktop で動作することを確認します。 Microsoft Managed Desktop は、Azure AD 組織 (テナント) で最後にチェックを実行してから 12 か月間、これらのチェックに関連付けられたデータを保持します。 12 か月後、匿名化された形式で保持します。 収集したデータを削除することを選択できます。

少なくともグローバル リーダーまたは Intune 管理者の役割を持っている人なら誰でもこのツールを実行できますが、2 つのチェック ([条件付きアクセス ポリシー](readiness-assessment-fix.md#conditional-access-policies)と[多要素認証](readiness-assessment-fix.md#multifactor-authentication)には追加のアクセス許可が必要です)。

> [!IMPORTANT]  
> オンライン準備評価ツールは、Microsoft マネージド デスクトップに初めて登録する準備ができているかどうかを確認するのに役立ちます。 組織が既に Microsoft マネージド デスクトップに登録されている場合は、このツールを使用しないでください。

評価ツールは次の項目をチェックします。

## <a name="microsoft-intune-settings"></a>Microsoft Intune 設定

|チェック  |説明  |
|---------|---------|
|Autopilot 展開プロファイル     | オートパイロット展開プロファイルの割り当てがすべてのデバイスに適用されるわけではないことを確認します (プロファイルを Microsoft 管理対象デスクトップ デバイスに割り当て *ない* でください)。       |
|証明書コネクタ     | 証明書コネクタの状態をチェックして、それらがアクティブであることを確認します   |
|条件付きアクセス     | 条件付きアクセス ポリシーがすべてのユーザーに割り当てられていないことを確認します (条件付きアクセス ポリシーは、Microsoft Managed Desktop サービス アカウントに割り当て *ない* でください)。    |
|デバイス コンプライアンス ポリシー     | Intune コンプライアンス ポリシーがすべてのユーザーに割り当てられていないことを確認します (ポリシーは Microsoft 管理対象デスクトップ デバイスに割り当て *ない* でください)。    |
|デバイスの構成プロファイル     | 構成プロファイルがすべてのユーザーまたはすべてのデバイスに割り当てられていないことを確認します (構成プロファイルを Microsoft 管理対象デスクトップ デバイスに割り当て *ない* でください)。     |
|デバイスの種類の制限     | 組織内の Windows 10 デバイスが Intune への登録を許可されていることを確認します        |
|登録ステータス ページ     | 登録ステータス ページが有効になっていないことを確認します      |
|Intune の登録     | Azure AD 組織内の Windows 10 デバイスが Intune に自動的に登録されていることを確認します         |
|ビジネス向け Microsoft Store     | ビジネス向け Microsoft Store が有効になっていて、Intune と同期されていることを確認します        |
|多要素認証 | 多要素認証が Microsoft Managed Desktop サービス アカウントに適用されていないか確認します。
|PowerShell スクリプト     | Windows PowerShell スクリプトが Microsoft Managed Desktop デバイスを対象とする方法で割り当てられて *いない* ことを確認します    |
|地域     | お住まいの地域が Microsoft Managed Desktop でサポートされていることを確認します        |
|セキュリティ基本計画     | セキュリティ ベースライン プロファイルがすべてのユーザーまたはすべてのデバイスを対象としていないことを確認します (セキュリティ ベースライン ポリシーは、Microsoft Managed Desktop デバイスを対象と *しないで* ください)。       |
|Windows アプリ     | Microsoft Managed Desktop デバイスに割り当てるアプリを確認します      |
|Windows Hello for Business     | Windows Hello for Business が有効になっていることを確認します        |
|Windows 10 更新リング     | Intune の "Windows 10 更新リング" ポリシーがすべてのユーザーまたはすべてのデバイスを対象としていないことを確認します (ポリシーは Microsoft Managed Desktop を対象と *しない* でください)。     |

## <a name="azure-active-directory-settings"></a>Azure Active Directory の設定

|チェック  |説明  |
|---------|---------|
|Enterprise State Roaming の "アドホック" サブスクリプション     | ("false" に設定されている場合) Enterprise State Roaming が正しく機能しない可能性がある設定を確認する方法をアドバイスします  |
|Enterprise State Roaming     | Enterprise State Roaming が有効になっていることを確認する方法をアドバイスします       |
|ライセンス     | 必要な[ライセンス](prerequisites.md#more-about-licenses)を取得していることを確認します         |
|多要素認証     | 多要素認証がすべてのユーザーに適用されないか確認します (多要素認証を Microsoft Managed Desktop サービス アカウントに誤って適用する必要はありません)。|
|セキュリティ アカウント名   | Microsoft Managed Desktop が独自に使用するために予約しているユーザー名と競合するユーザー名がないことを確認します        |
|セキュリティ管理者の役割     | セキュリティ リーダー、セキュリティ オペレーター、またはグローバル リーダーの役割を持つユーザーに、Microsoft Defender for Endpoint でこれらの役割が割り当てられていることを確認します         |
|セキュリティの既定値 | Azure AD 組織で Azure Active Directory でセキュリティの既定値が有効になっているかどうかを確認します |
|セルフサービスによるパスワードのリセット     | セルフサービス パスワード リセットが有効になっていることを確認します        |
|標準ユーザーの役割     | ユーザーが標準ユーザーであり、ローカル管理者権限を持っていないことを確認します         |

## <a name="microsoft-365-apps-for-enterprise-settings"></a>エンタープライズ設定用の Microsoft 365 Apps

|チェック  |説明  |
|---------|---------|
|OneDrive for Business     | OneDrive for Business がサポートされていない設定を使用しているかどうかを確認します。        |

チェックごとに、ツールは 4 つの考えられる結果のいずれかを報告します。

|結果  |意味  |
|---------|---------|
|準備完了     | 登録を完了する前にアクションは必要ありません。        |
|アドバイザリ    | 登録とユーザーにとって最高のエクスペリエンスを得るには、ツールの手順に従ってください。 登録を完了することは *できます* が、最初のデバイスを展開する前にこれらの問題を修正する必要があります。        |
|使用不可能 | これらの問題を修正しないと、*登録は失敗します*。 ツールの手順に従って解決します。        |
|Error | 使用してい るAzure Active Director (AD) の役割には、このチェックを実行するための十分なアクセス許可がありません。 |

## <a name="after-enrollment"></a>登録した後

Microsoft Managed Desktop への登録が完了したら、戻って特定の Intune および Azure AD 設定を調整することを忘れないでください。 詳細については、「[登録後に設定を調整する](../get-started/conditional-access.md)」を参照してください。

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop の準備をする手順

1. [Microsoft マネージド デスクトップの前提条件](prerequisites.md)を確認します。
2. 準備評価ツール (この記事) を実行します。
3. [ポータル サイト](../get-started/company-portal.md)を購入します。
4. [ゲスト アカウントの前提条件](guest-accounts.md)を確認します。
5. [ネットワーク構成](network.md)をチェックします。
6. [証明書とネットワーク プロファイル](certs-wifi-lan.md)を準備します。
7. [データへのユーザー アクセスを準備します](authentication.md)。
8. [アプリを準備します](apps.md)。
9. [マップ済みドライブを準備します](mapped-drives.md)。
10. [印刷リソースを準備します](printing.md)。
11. [デバイス名](address-device-names.md)をアドレス指定します。
