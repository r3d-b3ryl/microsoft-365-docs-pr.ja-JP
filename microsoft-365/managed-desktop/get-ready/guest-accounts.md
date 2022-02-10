---
title: ゲスト アカウントの前提条件
description: ゲスト アカウントの構成ガイドラインと調整方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 80770c6c122cc4e2892c22a43f185ffbac40c637
ms.sourcegitcommit: cafca45069819a44c7cf8c67f6c1e105de1b3393
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2022
ms.locfileid: "62520416"
---
# <a name="prerequisites-for-guest-accounts"></a>ゲスト アカウントの前提条件

## <a name="external-collaboration-settings"></a>外部コラボレーションの設定

Microsoft Managed Desktop では、ゲスト アカウント アクセス用に組織でAzure AD構成をお勧めします。 これらの設定は、 [Azure portal の [外部](https://portal.azure.com) ID **/ 外部コラボレーション設定] で調整できます**。

| Setting | 設定値 |
| ------ | ------ |
| ゲスト アクセス | ゲストは、ディレクトリ オブジェクトのプロパティとメンバーシップへのアクセスが制限されています。 |
| ゲスト招待設定 | 特定の管理者ロールに割り当てられたメンバー ユーザーとユーザーは、メンバーのアクセス許可を持つゲストを含むゲストを招待できます |

Microsoft Managed Desktop では、ゲスト アカウント アクセス用に組織Azure AD構成が必要です。 この設定は、 [Azure portal の [外部](https://portal.azure.com) ID/ 外部コラボレーション **設定] で調整できます**。

| Setting | オプション |
| ------ | ------ |
| 共同作業における制限事項 | 次のオプションを選択します。 <ul><li>[任意の **ドメインへの招待の** 送信を許可する ( 最も包括的な) ] を選択した場合、他の構成は必要ありません。</li><li>[指定した **ドメインへの** 招待を拒否する] を選択した場合は、Microsoft.com ドメインに一覧が表示されていないか確認します。</li><li>[指定した **ドメイン** への招待のみを許可する ( 最も制限が厳しい) ] を選択した場合は、Microsoft.com  がターゲット ドメインに表示されます。</li><ul>

これらの設定を操作する制限を設定する場合は、モダン Workplace サービス Azure Active Directory **を除外してください**。 たとえば、ゲスト アカウントによる Intune ポータルへのアクセスを妨げる条件付きアクセス ポリシーがある場合は、このポリシーからモダン **Workplace サービス** アカウント グループを除外します。

詳細については、「 [B2B 外部コラボレーションを有効にし、ゲストを招待できるユーザーを管理する」を参照してください](/azure/active-directory/external-identities/delegate-invitations#to-configure-external-collaboration-settings)。

## <a name="unlicensed-intune-admin"></a>ライセンスのない Intune 管理者

[ **ライセンスのない管理者へのアクセスを許可する] 設定** を有効にする必要があります。 この設定を有効にしない場合、サービスを提供する組織にアクセスしようとAzure ADが発生する可能性があります。 セキュリティへの影響を気にすることなく、この設定を安全に有効にできます。 アクセス範囲は、運用スタッフを含むユーザーに割り当てられた役割によって定義されます。

**この設定を有効にするには、次の方法を使用します。**

1. 管理センターのMicrosoft エンドポイント マネージャー[移動します](https://go.microsoft.com/fwlink/?linkid=2109431)。
2. [テナントの **管理] に移動し、[** 役割] を **選択します**。 次に、[ **管理者ライセンス] を選択します**。
3. [ライセンス **のない管理者へのアクセスを許可する] セクション** で、[はい] を **選択します**。

> [!IMPORTANT]
> [はい] を選択した後は、この設定を元に戻 **すことはできません**。

詳細については、「ライセンスのない管理者」を[参照Microsoft Intune](/mem/intune/fundamentals/unlicensed-admins)。

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop の準備をする手順

1. [Microsoft マネージド デスクトップの前提条件](prerequisites.md)を確認します。
1. [準備状況の評価ツール](readiness-assessment-tool.md)を実行します。
1. [ポータル サイト](../get-started/company-portal.md)を購入します。
1. ゲスト アカウントの前提条件を確認します (この記事)。
1. [ネットワーク構成](network.md)をチェックします。
1. [証明書とネットワーク プロファイル](certs-wifi-lan.md)を準備します。
1. [データへのユーザー アクセスを準備します](authentication.md)。
1. [アプリを準備します](apps.md)。
1. [マップ済みドライブを準備します](mapped-drives.md)。
1. [印刷リソースを準備します](printing.md)。
1. [デバイス名](address-device-names.md)をアドレス指定します。
