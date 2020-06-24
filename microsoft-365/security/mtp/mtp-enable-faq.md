---
title: Microsoft の脅威保護を有効にする際によく寄せられる質問
description: Microsoft の脅威保護を有効にするためのライセンス、アクセス許可、初期設定、その他の製品およびサービスに関してよく寄せられる質問に対する回答を取得します。
keywords: よく寄せられる質問、FAQ、GCC、作業の開始、MTP の有効化、Microsoft Threat Protection、M365、セキュリティ、データの場所、必要なアクセス許可、ライセンス資格情報、設定ページ
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 9dcfeb5616afc8953e862d6d1a542d694582b157
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "44845072"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a>Microsoft の脅威保護を有効にする際によく寄せられる質問

**適用対象:**
- Microsoft Threat Protection

必要なライセンスとアクセス許可、サポートサービスの展開、初期設定など、 [Microsoft の脅威保護](microsoft-threat-protection.md)を有効にすることに関してよく寄せられる質問に対する回答を確認できます。

サービスを有効にする方法については、「 [Microsoft Threat Protection を有効](mtp-enable.md)にする」を参照してください。

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a>Microsoft 365 E5 ライセンスがありません。 Microsoft の脅威保護を引き続き使用できますか。

次の E5 以外のライセンスを持つお客様は、Microsoft の脅威保護を使用できます。

- Microsoft Defender Advanced Threat Protection
- Azure Advanced Threat Protection
- Microsoft Cloud App Security
- Office 365 Advanced Threat Protection (プラン 2)
 
サポートされているライセンスの完全な一覧については、[ライセンス要件を参照](prerequisites.md#licensing-requirements)してください。

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a>Microsoft の脅威保護の使用を開始するには、何をインストールまたは展開する必要がありますか。

いいえ。 Microsoft の脅威保護は、既に展開されている Microsoft 365 セキュリティサービスからのデータを統合します。 オンにすると、インシデント、自動化、および検索のエクスペリエンスは、展開された製品の範囲内で動作し始めます。 これらの製品のいずれも適切に展開されていない場合、Microsoft の脅威保護ではデータは表示されず、操作を行うことはできません。

Microsoft の脅威保護エクスペリエンスを最適化するために、サポートされている*すべて*の[microsoft 365 セキュリティ製品とサービス](deploy-supported-services.md)を展開することをお勧めします。

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a>Microsoft の脅威保護のプロセスとデータの保存場所
Microsoft の脅威保護は、統合されたデータを処理および保存するデータセンターの最適な場所を自動的に選択します。 Microsoft Defender ATP がある場合は、Microsoft Defender ATP で使用されているものと同じ場所を選択します。

>[!NOTE]
>Microsoft Defender ATP は、Azure セキュリティセンターを使用してオンにした場合に、欧州連合 (EU) のデータセンターで自動的にプロビジョニングされます。 Microsoft の脅威保護は、Microsoft Defender ATP をこの方法でプロビジョニングしたお客様に対して、同じ EU データセンターで自動的にプロビジョニングされます。 

データセンターの場所は、Microsoft Threat Protection (**設定 > Microsoft Threat protection**) の設定ページで、サービスの準備が完了する前と後に表示されます。 別のデータセンターの場所を使用する場合は、microsoft 365 セキュリティセンターの microsoft サポートに問い合わせて、[**ヘルプが必要ですか?** ] を選択します。

## <a name="where-can-i-access-microsoft-threat-protection"></a>Microsoft の脅威保護にはどこでアクセスできますか?

Microsoft の脅威保護は、Microsoft 365 セキュリティセンターで利用できます。 セキュリティセンターに移動するには、URL を参照し [https://security.microsoft.com](https://security.microsoft.com) ます。

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a>Microsoft 365 セキュリティセンターの Microsoft 脅威保護にアクセスするために必要なアクセス許可は何ですか。

次の Azure Active Directory (AD) のロールが割り当てられているアカウントは、Microsoft Threat Protection の機能とデータにアクセスできます。

- グローバル管理者
- セキュリティ管理者
- セキュリティ オペレーター
- グローバル閲覧者
- セキュリティ閲覧者

>[!NOTE]
>Microsoft Defender ATP の役割ベースのアクセス制御の設定は、データへのアクセスに影響します。 詳細については、「 [Microsoft の脅威保護へのアクセスの管理](mtp-permissions.md)について」を参照してください。

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a>Microsoft の脅威保護の既定のタイムゾーンは何ですか。
既定では、Microsoft Threat Protection は UTC タイムゾーンで時間情報を表示します。 この設定を変更して、ローカルタイムゾーンを使用することができます。 [タイムゾーンの設定について](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a>Microsoft の新しい脅威保護機能と UI 更新プログラムについて調べるにはどうすればよいですか?

Microsoft では、次のようなさまざまなチャネルで情報を定期的に提供しています。

- Microsoft 365 管理センターの[メッセージセンター](../../admin/manage/message-center.md)
- [Microsoft 365 security & コンプライアンスの技術コミュニティ](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)におけるブログ投稿

[プレビュー機能](preview.md)を有効にして、一般公開されている最新のエクスペリエンスを取得できます。

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Microsoft Threat Protection は、米国政府機関向けコミュニティ クラウド (GCC) または GCC High で使用できますか?
現時点では、使用できません。

## <a name="related-topics"></a>関連項目

- [Microsoft Threat Protection の概要](microsoft-threat-protection.md)
- [Microsoft の脅威保護を有効](mtp-enable.md)にします。
- [ライセンス要件およびその他の前提条件](prerequisites.md)
- [サポートされるサービスを展開する](deploy-supported-services.md)
- [プレビュー機能を有効にする](preview.md)