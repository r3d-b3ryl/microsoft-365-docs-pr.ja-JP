---
title: PST ファイルのインポートに関する FAQ
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
ms.custom: seo-marvel-apr2020
description: この記事では、Office 365 インポートサービスを使用して Microsoft 365 に PST ファイルをインポートする際に、管理者がよく寄せられる質問に対する回答を示します。
ms.openlocfilehash: 0f490b7bae3f462bb07725bf14453a6b9a4d7b9e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817736"
---
# <a name="faq-about-importing-pst-files"></a>PST ファイルのインポートに関する FAQ

**この記事は、管理者を対象としています。PST ファイルを自分のメールボックスにインポートしますか?「 [Outlook .pst ファイルからメール、連絡先、予定表をインポートする](https://go.microsoft.com/fwlink/p/?LinkID=785075)」を参照してください。**|
   
Office 365 インポートサービスを使用して PST ファイルを Microsoft 365 メールボックスに一括インポートする方法についてよく寄せられる質問を以下に示します。 PST ファイルのインポート方法の詳細については、「 [365 Office 2010 への pst ファイルのインポートの概要](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365)」を参照してください。
  
## <a name="using-network-upload-to-import-pst-files"></a>ネットワーク アップロードを使用して PST ファイルをインポートする

詳細な手順については、「[ネットワークアップロードを使用して PST ファイルを Office 365 にインポート](use-network-upload-to-import-pst-files.md)する」を参照してください。
  
 **Office 365 インポート サービスでインポート ジョブを作成するにはどのようなアクセス許可が必要ですか?**
  
PST ファイルを Microsoft 365 メールボックスにインポートするには、Exchange Online で Mailbox Import Export の役割が割り当てられている必要があります。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は "Organization Management/組織の管理" 役割グループに追加できます。 または、新しい役割グループを作成し、Mailbox Import Export 役割を割り当て、自分や他のユーザーをメンバーとして追加できます。 詳細については、「[Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)」 (Exchange Online の役割グループの管理) の "Add a role to a role group" (役割グループに役割を追加する) または "Create a role group" (役割グループを作成する) を参照してください。
  
さらに、セキュリティ/コンプライアンス センターでインポート ジョブを作成するには、次のいずれかを満たす必要があります。
  
- Exchange Online で Mail Recipients の役割が割り当てられている必要があります。 既定では、この役割は Organization Management 役割グループと Recipient Management 役割グループに割り当てられます。
    
    または
    
- 組織の全体管理者である必要があります。
    
> [!TIP]
> PST ファイルを Office 365 にインポートするための新しい役割グループを Exchange Online で作成することを検討します。 PST ファイルをインポートするのに必要な最小レベルの権限では、新しい役割グループに Mailbox Import Export の役割および Mail Recipients の役割を割り当て、メンバーを追加します。 
  
 **ネットワーク アップロードはどこで利用できますか?**
  
ネットワークアップロードは現在、米国、カナダ、ブラジル、英国、フランス、ヨーロッパ、インド、東アジア、東南アジア、日本、韓国、オーストラリア、アラブ首長国連邦 (UAE) の各地域で利用できます。 Network upload will be available in more regions soon.

> [!NOTE]
> 現時点では、PST ファイルのネットワーク アップロードはドイツとスイスでは利用できません。 この FAQ は、これらの国でネットワーク アップロードが利用可能になると更新されます。
  
 **ネットワーク アップロードを使用して PST ファイルをインポートすると、料金はいくらですか?**
  
Using network upload to import PST files is free.
  
つまり、PST ファイルが Azure Storage 領域から削除されると、Microsoft 365 管理センターでは、完了済みインポート ジョブのファイル一覧から PST ファイルの表示が消えます。 インポート ジョブは引き続き [**Office 365 へのデータのインポート**] ページに表示されることがありますが、古いインポート ジョブの詳細を表示すると、PST ファイルの一覧は空になっている可能性があります。 
  
 **Office 365 へのインポートがサポートされている PST ファイル形式のバージョンは何ですか?**
  
PST ファイル形式には、ANSI と Unicode という 2 つのバージョンがあります。 Unicode PST ファイル形式を使用したファイルをインポートすることをお勧めします。 ただし、2 バイト文字セット (DBCS) を使用する言語のファイルのように、ANSI PST ファイル形式を使用したファイルも Office 365 にインポートできます。 ANSI PST ファイルのインポートの詳細については、「[ネットワークアップロードを使用して組織の pst ファイルを Office 365 にインポートする](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file)」の手順4を参照してください。
  
また、Outlook 2007 以降のバージョンの PST ファイルを Office 365 にもインポートできます。
  
 **Azure Storage 領域に PST ファイルをアップロードした後、ファイルが削除されるまで、どれくらいの期間 Azure に保持されますか?**
  
ネットワーク アップロードの方法を使用して PST ファイルをインポートする場合、ファイルは **ingestiondata** という Azure の blob コンテナーにアップロードします。 セキュリティ/コンプライアンス センター の [**PST ファイルのインポート**] ページで進捗中のインポート ジョブがない場合、一番新しいインポート ジョブが セキュリティ/コンプライアンス センター で作成されてから 30 日後に、Azure の **ingestiondata** コンテナーにあるすべての PST ファイルが削除されます。 つまり、ユーザーは PST ファイルを Azure にアップロードしてから 30 日以内に、(ネットワークのアップロード手順の手順 5 で示すように) セキュリティ/コンプライアンス センター で新しいインポート ジョブを作成する必要があります。 
  
つまり、PST ファイルが Azure Storage 領域から削除されると、セキュリティ/コンプライアンス センターでは、完了済みインポート ジョブのファイル一覧から PST ファイルの表示が消えます。 インポート ジョブがセキュリティ/コンプライアンス センター の [**PST ファイルのインポート**] ページの一覧に引き続き表示されていても、以前のインポート ジョブの詳細を表示すると、PST ファイルの一覧は空になっている可能性があります。 
  
 **メールボックスに PST ファイルをインポートするには、どれぐらい時間がかかりますか?**
  
ネットワークの性能によって異なりますが、一般的には組織の Azure Storage 領域にアップロードするデータ 1 TB あたり数時間かかります。 PST ファイルが Azure Storage 領域にコピーされると、各 PST ファイルは 1 日あたり 24 GB 以上の速度で Microsoft 365 のメールボックスにインポートされます。 この速度ではニーズを満たさない場合、メール データを Office 365 に移行するための他の方法も検討できます。 詳細については、「[複数のメール アカウントを Office 365 に移行する方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)」を参照してください。
  
複数の PST ファイルを異なる複数のメールボックスにインポートする場合、インポート プロセスは並行して実行されます。つまり、対になるそれぞれの PST とメールボックスが同時にインポートされます。 同様に、複数の PST ファイルを同じメールボックスにインポートする場合も、同時にインポートされます。
  
 **PST インポート プロセスでは、重複するメールアイテムはどのように処理されますか?**

PST　インポート プロセスによってアイテムの重複がチェックされます。インポート先のメールボックス内またはインポート先のアーカイブ内のインポート先フォルダーに一致するアイテムがある場合、一致するアイテムは PST ファイルからメールボックスまたはアーカイブにコピーされません。 同じ PST ファイルをインポートして、(PST インポート マッピング ファイルの TargetRootFolder プロパティを使用して) 異なるインポート先フォルダーを指定すると、その PST ファイル内のすべてのアイテムが再インポートされます。

 **PST ファイルをインポートするときにメッセージ サイズに制限はありますか?**
  
はい。 PST ファイルに 150 MB を超えるメールボックス アイテムが含まれる場合、インポート プロセスではアイテムがスキップされます。
  
 **メッセージの送受信時刻や受信者のリストなどのメッセージ プロパティは、PST ファイルを Microsoft 365 メールボックスにインポートするときに保持されますか?**
  
はい。 インポート プロセス中は、元のメッセージのメタデータが変更されることはありません。
  
 **メールボックスにインポートする PST ファイルのフォルダー階層のレベルの数に制限はありますか?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **ネットワーク アップロードを使用して PST ファイルを Office 365 の非アクティブなメールボックスにインポートすることはできますか?**
  
Yes, this capability is now available. 
  
 **ネットワーク アップロードを使用して、Exchange ハイブリッド展開のオンライン アーカイブ メールボックスに PST ファイルをインポートできますか?**
  
はい、この機能は現在利用できるようになっています。
  
 **ネットワーク アップロードを使用して PST ファイルを Exchange Online のパブリック フォルダーにインポートできますか?**
  
いいえ、PST ファイルをパブリック フォルダーにはインポートできません。
  
## <a name="using-drive-shipping-to-import-pst-files"></a>ドライブ送付を使用して PST ファイルをインポートする

詳細な手順については、「 [drive 送料を使用して PST ファイルを Office 365 にインポートする](use-drive-shipping-to-import-pst-files-to-office-365.md)」を参照してください。
  
 **Office 365 インポート サービスでインポート ジョブを作成するにはどのようなアクセス許可が必要ですか?**
  
PST ファイルを Microsoft 365 メールボックス にインポートするには、Mailbox Import Export の役割を割り当てる必要があります。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は "Organization Management/組織の管理" 役割グループに追加できます。 または、新しい役割グループを作成し、Mailbox Import Export 役割を割り当て、自分や他のユーザーをメンバーとして追加できます。 詳細については、「[Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)」 (Exchange Online の役割グループの管理) の "Add a role to a role group" (役割グループに役割を追加する) または "Create a role group" (役割グループを作成する) を参照してください。
  
さらに、セキュリティ/コンプライアンス センターでインポート ジョブを作成するには、次のいずれかを満たす必要があります。
  
- Exchange Online で Mail Recipients の役割が割り当てられている必要があります。 既定では、この役割は Organization Management 役割グループと Recipient Management 役割グループに割り当てられます。
    
    または
    
- 組織の全体管理者である必要があります。
    
> [!TIP]
> PST ファイルを Office 365 にインポートするための新しい役割グループを Exchange Online で作成することを検討します。 PST ファイルをインポートするのに必要な最小レベルの権限では、新しい役割グループに Mailbox Import Export の役割および Mail Recipients の役割を割り当て、メンバーを追加します。 
  
 **ドライブ送付はどこで利用できますか?**
  
現在のところ、ドライブ送付は米国、カナダ、ブラジル、イギリス、欧州、インド、東アジア、東南アジア、日本、韓国、オーストラリアでご利用いただけます。 ドライブ送付はその他の地域でも間もなくご利用いただけるようになります。

> [!NOTE]
> 現時点では、PST ファイルをインポートするためのドライブ送付は、ドイツとスイスでは利用できません。 この FAQ は、これらの国でドライブ送付が利用可能になると更新されます。
  
 **ドライブ送付をサポートする商用の使用許諾契約は何ですか?**
  
Microsoft 365 に PST ファイルをインポートするためのドライブ送付は Microsoft Enterprise Agreement (EA) で利用できます。 Microsoft Products and Services Agreement (MPSA) では、ドライブ送付はご利用いただけません。
  
 **ドライブの発送を使用して PST ファイルを Microsoft 365 にインポートすると、料金はいくらですか?**
  
ドライブの発送を使用して PST ファイルを Microsoft 365 メールボックスにインポートするコストは、1 GB のデータあたり 2 米ドルです。 たとえば、1,000 GB (1 TB) の PST ファイルを含むハード ディスク ドライブを発送する場合のコストは、2,000 米ドルです。 インポート手数料は、パートナーと分担して支払うことができます。 パートナーを探す方法については、「[Microsoft パートナーまたは販売店を探す](https://go.microsoft.com/fwlink/p/?LinkId=785197)」を参照してください。
  
 **ドライブ発送では、どのような種類のハード ドライブがサポートされていますか?**
  
Office 365 インポート サービスでは、2.5 インチのソリッドステート ドライブ (SSD) または 2.5 インチまたは 3.5 インチの SATA II/III 内部ハード ドライブのみがサポートされています。 最大で 10 TB のハード ドライブを使用できます。 インポート ジョブでは、ハード ドライブの最初のデータ ボリュームのみが処理されます。 このデータ ボリュームは、NTFS でフォーマットする必要があります。 データをハード ドライブにコピーする場合、2.5 インチ SSD、2.5 または 3.5 インチ SATA II/III コネクタを使用して直接接続するか、外部 2.5 インチ SSD、2.5 または 3.5 インチ SATA II/III USB アダプターを使用して外付けできます。
  
> [!IMPORTANT]
> Office 365 インポート サービスでは、USB アダプターが内蔵されている外部ハード ドライブはサポートされていません。 また、外部ハード ドライブのケース内にあるディスクは使用できません 外部ハード ドライブは発送しないでください。 
  
 **1 回のインポート ジョブで発送できるハード ディスク ドライブの数はいくつですか?**
  
1 回のインポート ジョブで最大 10 台のハード ディスク ドライブを発送できます。
  
 **ハードドライブを送付した後、Microsoft データ センターに到着するまでどのくらいの時間がかかりますか?**
  
That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.
  
 **Microsoft のデータ センターにハード ドライブが到着してから PST ファイルが Azure にアップロードされるまで、どれくらいかかりますか?**
  
Microsoft データセンターでハードドライブを受信した後は、組織の Azure ストレージ領域に PST ファイルをアップロードするために、7 ~ 10 営業日かかります。 PST ファイルは、 **ingestiondata**という名前の Azure blob コンテナーにアップロードされます。 
  
 **メールボックスに PST ファイルをインポートするには、どれぐらい時間がかかりますか?**
  
PST ファイルが Azure Storage 領域にアップロードされると、Microsoft 365 が (セキュリティで保護された安全な方法で) PST ファイル内のデータを分析して、アイテムの経過時間と、PST ファイルに含まれるさまざまなメッセージの種類を識別します。 この分析が完了したら、PST ファイルのすべてのデータをインポートしたり、フィルターを設定してインポートするデータを制御したりできます。 インポート ジョブを開始した後、PST ファイルは 1 日に少なくとも 24 GB の速さで Microsoft 365 メールボックスにインポートされます。 このレートでは要件を満たさない場合は、メール データを Office 365 にインポートするための別の方法も検討できます。 詳細については、「[複数のメール アカウントを Office 365 に移行する方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)」を参照してください。
  
複数の PST ファイルを異なる複数のメールボックスにインポートする場合、インポート プロセスは並行して実行されます。つまり、対になるそれぞれの PST とメールボックスが同時にインポートされます。 同様に、複数の PST ファイルを同じメールボックスにインポートする場合も、同時にインポートされます。
  
 **Microsoft が私の PST ファイルを Azure にアップロードした後、削除されるまで、どのくらいの期間 Azure に保持されますか?**
  
**Ingestiondata**という名前の blob コンテナー内の組織の Azure ストレージの場所にあるすべての pst ファイルは、最新のインポートジョブが、セキュリティ & コンプライアンスセンターの [ **PST ファイルのインポート**] ページで作成されてから30日後に削除されます。 
  
つまり、PST ファイルが Azure Storage 領域から削除されると、セキュリティ/コンプライアンス センターでは、完了済みインポート ジョブのファイル一覧から PST ファイルの表示が消えます。 インポート ジョブがセキュリティ/コンプライアンス センター の [**PST ファイルのインポート**] ページの一覧に引き続き表示されていても、以前のインポート ジョブの詳細を表示すると、PST ファイルの一覧は空になっている可能性があります。 
  
 **Microsoft 365 へのインポートがサポートされている PST ファイル形式のバージョンは何ですか?**
  
PST ファイル形式には、ANSI と Unicode という 2 つのバージョンがあります。 Unicode PST ファイル形式を使用したファイルをインポートすることをお勧めします。 ただし、2 バイト文字セット (DBCS) を使用する言語のファイルのように、ANSI PST ファイル形式を使用したファイルも Microsoft 365 にインポートできます。 ANSI PST ファイルのインポートの詳細については、「 [Use drive 送料 To Office 365 に PST ファイルをインポートする](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)」の手順3を参照してください。
  
また、Outlook 2007 以降のバージョンの PST ファイルを Office 365 にもインポートできます。
  
 **PST ファイルをインポートするときにメッセージ サイズに制限はありますか?**
  
はい。 PST ファイルに 150 MB を超えるメールボックス アイテムが含まれる場合、インポート プロセスではアイテムがスキップされます。
  
  **PST インポート プロセスでは、重複するメールアイテムはどのように処理されますか?**

PST　インポート プロセスによってアイテムの重複がチェックされます。インポート先のメールボックス内またはインポート先のアーカイブ内のインポート先フォルダーに一致するアイテムがある場合、一致するアイテムは PST ファイルからメールボックスまたはアーカイブにコピーされません。 同じ PST ファイルをインポートして、(PST インポート マッピング ファイルの TargetRootFolder プロパティを使用して) 異なるインポート先フォルダーを指定すると、その PST ファイル内のすべてのアイテムが再インポートされます。
 
 **メッセージの送受信時刻や受信者のリストなどのメッセージ プロパティは、PST ファイルを Microsoft 365 メールボックスにインポートするときに保持されますか?**
  
はい。 インポート プロセス中は、元のメッセージのメタデータが変更されることはありません
  
 **メールボックスにインポートする PST ファイルのフォルダー階層のレベルの数に制限はありますか?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **ドライブ発送を使用して PST ファイルを Microsoft 365 の非アクティブなメールボックスにインポートすることはできますか?**
  
はい、この機能は現在利用できるようになっています。
  
 **ドライブの発送を使用して、Exchange ハイブリッド展開のオンライン アーカイブ メールボックスに PST ファイルをインポートできますか?**
  
はい、この機能は現在利用できるようになっています。
  
 **ドライブの発送を使用して PST ファイルを Exchange Online のパブリック フォルダーにインポートできますか?**
  
いいえ、PST ファイルをパブリック フォルダーにはインポートできません。
  
 **Microsoft からハード ディスク ドライブが返送される前に、Microsoft はハード ディスク ドライブのデータを消去できますか?**
  
No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **Microsoft がハード ディスクを返送せずに処分してもかまいませんか?**
  
No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **返送時はどの宅配会社を利用できますか?**
  
If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.
  
 **返送の料金はいくらですか?**
  
Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.
  
 **Microsoft にハード ディスクを送付するとき、FedEx カスタム送付などの宅配会社のカスタム出荷サービスを使用できますか?**
  
はい。
  
 **ハード ドライブを別の国に送付しなければならない場合、何か必要な手続きはありますか? **
  
The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.
